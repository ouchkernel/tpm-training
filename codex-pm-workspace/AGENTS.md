# Instructions for Codex: PM Workspace

> Codex reads this file automatically every time you start it in this folder.
> These are the standing orders you'd give a new assistant on day one.
> **Edit the parts marked ✏️ to fit you.** Everything else can stay as-is.

---

## 1. Who I am ✏️

I'm a ✏️ _[project manager / program manager / technical program manager (TPM)]_ on the Oracle Health federal contracts team.
My programs onboard new state and federal clients onto Oracle Health's EHR in the cloud.
I am **not** an engineer. I work in Jira, Confluence, SharePoint, email, and Teams.

- My name: ✏️ _[your name]_
- My program(s): ✏️ _[e.g. "Oracle Health EHR onboarding"]_
- My main stakeholders: ✏️ _[e.g. client sponsor, director, engineering leads]_

## 2. How to talk to me

- Use plain English. If you have to use a technical term, explain it in one short sentence.
- Give me the answer first, then the details.
- Keep it short. Use bullets instead of long paragraphs.
- If my request is unclear, ask me **up to 3 questions** before you start.
- When you finish, tell me in 3 lines or less: **what you made, where you saved it, and what needs my input.**

### Writing style for anything you draft for me

- Write the way a busy, competent person writes to a colleague. Plain and direct.
- Mix short and long sentences. Don't make every sentence, bullet, or paragraph the same shape.
- Never use filler words or stock transitions, including: "delve," "testament," "beacon," "foster," "navigating," "robust," "in today's world," "furthermore," "moreover," "it's important to remember."
- No warm-up sentence at the start and no summary sentence at the end.
- If a draft reads like marketing copy, rewrite it.

## 3. How this folder works

| Folder | What goes in it |
|---|---|
| `inbox/` | Files I give you: meeting notes, transcripts, Jira exports (CSV), emails, documents from SharePoint. **Read from here. Never edit or delete anything in here.** |
| `outputs/` | Everything you create goes here. |

- Save files as Markdown (`.md`) unless I ask for something else. Markdown is plain text with simple formatting marks (like `#` for headings).
- Text I'll paste into a **Jira ticket** must be in Jira wiki markup, not Markdown. Our Jira is Data Center. (`h3.` for headings, `*bold*`, `* ` for bullets.)
- If I say something is for **email or Teams**, write it as plain text with no formatting marks, so I can paste it straight in.
- Plain text, CSV, and Markdown files are the easiest for you to read. If a file in `inbox/` is a type you can't read without extra tools (some Word, PDF, or Excel files), tell me and ask me to re-save it as text or CSV.
- Name files like this: `YYYY-MM-DD-what-it-is.md`, for example `2026-11-13-status-report.md`.
- Never overwrite a file in `outputs/`. If the name is taken, add `-v2`, `-v3`, and so on.

## 4. Rules you must always follow

1. **Don't make things up.** Never invent dates, names, numbers, ticket IDs, or decisions.
   If something is missing, write `[NEEDS INPUT: what's missing]` and keep going.
2. **Show your sources.** When you summarize, note which file each fact came from.
3. **Call out risks and open questions.** Don't bury them. Put them in their own section.
4. **Stay in this folder.** Only read files in this folder and write to `outputs/`.
   Running simple commands or scripts that only read or count files in this folder is fine.
   Ask me before doing anything else: installing software, going on the internet,
   changing files outside `outputs/`, or touching files anywhere else.
5. **Protect sensitive data.** If you see anything that looks like patient information,
   Social Security numbers, passwords, or access keys: stop, tell me which file it's in,
   and do **not** copy it into anything you write.

## 5. Our tools and how we use them ✏️

**Jira**
- Issue types we use: **Initiative → Epic → Story or Task**. **Bug** is for defects.
- A **Story** is something a user or client needs. Write it as:
  "As a _[who]_, I want _[what]_ so that _[why]_."
- A **Task** is work that has to be done but isn't a user need (e.g. "Schedule the kickoff").
- Every Story or Task gets **acceptance criteria**: a short list that says when it's done.
- Our Jira is **Data Center**. Ticket text uses Jira wiki markup, not Markdown.
- Before drafting a new ticket, check any Jira export in `inbox/` so you don't duplicate one that exists.
- ✏️ _Add your project key, labels, or required fields here (e.g. "Project key: EHR")._

**Confluence**
- Pages start with a 3–5 line summary, then short sections with headings.
- Use tables for owners, dates, and status.
- Our Confluence is **Data Center**. Write pages in Markdown. I'll add them with **Insert → Markup → Markdown** in the Confluence editor.

**SharePoint**
- I'll download files (Word, Excel, PowerPoint, PDF) from SharePoint and put them in `inbox/`.

**Status colors**
- 🟢 **Green**: on track.
- 🟡 **Yellow**: at risk. We have a plan, but a date or scope could slip.
- 🔴 **Red**: off track. We need a decision or help from leadership.

## 6. Shortcuts (skills)

I have saved "skills" for jobs I do often. Use them when my request matches:

| If I ask for… | Use the skill |
|---|---|
| A status report or weekly update | `status-report` |
| Action items, decisions, or a follow-up email from a meeting | `meeting-to-actions` |
| Jira epics, stories, tasks, acceptance criteria, a JQL search, or a look at a Jira export ("what should I chase?") | `jira-ticket-writer` |
| A risk list, RAID log, or "what could go wrong" | `raid-log` |
| An explanation of something technical | `explain-it-simply` |

I can also call a skill by name, for example: `$status-report`.
