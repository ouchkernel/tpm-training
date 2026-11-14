---
name: jira-ticket-writer
description: Draft Jira Initiatives, Epics, Stories, Tasks, and Bugs with clear summaries, descriptions, and acceptance criteria, or clean up and analyze existing tickets from a Jira CSV export. Use when the user asks for Jira tickets, stories, epics, acceptance criteria, a backlog, a JQL query, or an analysis of a Jira export.
---

# Jira ticket writer

Our Jira is **Jira Data Center**. Two things follow from that:
- Ticket text uses **Jira wiki markup**, not Markdown (see "Formatting" below).
- Jira links tickets with two different fields: **Epic Link** (a Story or Task to its Epic) and **Parent Link** (an Epic to its Initiative, if our Jira has that field).

## Our issue types

- **Initiative**: a big goal that spans months (e.g. "Oracle Health EHR onboarding").
- **Epic**: a chunk of an initiative that can be finished in weeks (e.g. "Identity and access setup").
- **Story**: something a user or client needs. Format: "As a [who], I want [what] so that [why]."
- **Task**: work to be done that isn't a user need (e.g. "Book the go-live readiness review").
- **Bug**: something that's broken.

## Drafting new tickets

1. Read the source (notes, a requirements doc, or the user's description).
2. **Check for existing tickets first.** If there's a Jira export in `inbox/`, compare each piece of work against it. Don't draft a ticket for work that already has one. List those under "Already in Jira" with the ticket key, and suggest an update to the existing ticket if the source adds something new (a date, an owner, a blocker).
3. Group the remaining work: Initiative → Epics → Stories and Tasks. Attach new Stories and Tasks to an existing Epic where one fits.
4. For each new ticket, fill in the template below.
5. Save to `outputs/YYYY-MM-DD-jira-drafts-[topic].md`, and also as a CSV
   (`outputs/YYYY-MM-DD-jira-drafts-[topic].csv`) with these columns:
   `Issue Type, Summary, Description, Acceptance Criteria, Epic Name, Epic Link, Parent Link, Labels`
   - **Epic Name**: fill in for Epics only.
   - **Epic Link**: for a Story, Task, or Bug, the Epic it belongs to. Use the existing Epic's key (e.g. EHR-20) when there is one.
   - **Parent Link**: for an Epic, the key of the Initiative it belongs to.
6. Tell the user the CSV is a draft for their Jira admin, not something to import as-is. Field names and linking rules depend on how our Jira is set up. Linking to a brand-new Initiative or Epic may take two imports: create the parents first, then the children. `[Confirm with the Jira admin]`

### Ticket template

In the saved `.md` file, put each ticket's Description and Acceptance criteria in a code block, written in Jira wiki markup, so the user can paste it straight into Jira.

```
[Issue type]: [Summary: start with a verb, under 80 characters]
Belongs to: [Epic or Initiative, with its key if it exists]

Description:
[2–4 sentences: what and why. For Stories, use "As a… I want… so that…".]

h3. Acceptance criteria
* [Something you can check: yes or no]
* ...

Open questions: [anything unclear, or "None"]
```

### Formatting (Jira wiki markup)

| To get | Type |
|---|---|
| A heading | `h3. Heading text` |
| Bold | `*bold*` |
| A bullet | `* item` |
| A numbered step | `# item` |
| A table | `||Header||Header||` then `|cell|cell|` |

Jira wiki markup has no checkboxes. Use bullets for acceptance criteria.

## Analyzing a Jira export (CSV)

When the user gives you a Jira CSV export, report:
- Counts by status and by assignee.
- Items that are **blocked**.
- Items that are **overdue**: the due date has passed **and the ticket is not Done**. Never list a Done ticket as overdue.
- Items that are **stale**: not updated in 14+ days, not counting Done tickets.
- Items with no assignee or no due date.
- The 5 things the PM should chase this week, with the reason for each.

Use the date the user gives as "today". If they don't give one, use today's date and say which date you used.

Real exports vary. Ours may have separate Epic Link and Parent Link columns, several columns all named Labels, and a Resolved date. Work with whatever columns are there, and say which ones you used.

Read the file only. Don't change it. Write the report to `outputs/`.

## Writing a JQL query

If the user asks for a Jira search, give them a JQL query they can paste into Jira's
advanced search, and explain each part in one line of plain English.

## Rules

- Acceptance criteria must be checkable: "Client can log in with SSO", not "SSO works well".
- One ticket = one thing. If a ticket has "and" in the summary, consider splitting it.
- Don't make up ticket numbers, people, or dates.
