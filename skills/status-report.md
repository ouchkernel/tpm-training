---
name: status-report
description: Write a weekly program status report or executive update from meeting notes, Jira exports, and other files in inbox/. Use when the user asks for a status report, weekly update, exec summary, or "where are we".
---

# Status report

## Steps

1. Settle the **reporting period**. If the user gives dates, use them. If not, use the 7 days ending today, and say so. Write the period at the top of the report.
2. Read the files in `inbox/` that the user points to. If they don't say which, read **every** file in `inbox/`, and list the ones you used with their dates. Don't skip a file because it's old: a charter or an unchanged Jira export can still matter. If a file looks out of date for this period, say so.
3. Work out the overall status (🟢 / 🟡 / 🔴) using the definitions in AGENTS.md. If you can't tell, mark it `[NEEDS INPUT: overall status]` and say why.
4. Write the report using the template below. Keep the whole thing to one page.
5. Save it to `outputs/YYYY-MM-DD-status-report.md`, using the last day of the reporting period as the date.
6. Tell the user what's in it and list every `[NEEDS INPUT]` you left.

## Template

```
# [Program name] status report, [date]

**Reporting period:** [start date] to [end date]
**Overall: 🟢/🟡/🔴.** [One sentence on why.]

## Summary
[3 bullets max. What a director needs to know in 30 seconds.]

## Progress this period
- ...

## Coming up next
- ...

## Risks and issues
| Risk / issue | Impact | Owner | What we're doing about it |
|---|---|---|---|

## Decisions or help needed
- [Who needs to decide what, and by when. Write "None" if there are none.]

## Key dates
| Milestone | Target date | Status |
|---|---|---|

_Sources: [list the files used, with their dates]_
```

## Rules

- Don't soften bad news. If something is late, say it's late.
- Don't invent dates or owners. Use `[NEEDS INPUT]`.
- Only list something under "Progress this period" if a source shows it happened in the period. A Jira export often can't prove *when* a ticket was finished. If the export has a Resolved date, use it. If it only has an Updated date, use that and add "(date approximate)".
- If the user says the audience is executives, cut "Progress this period" down to 3 bullets and lead with decisions needed.
