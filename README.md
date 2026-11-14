# PM / TPM AI Starter Kit (ChatGPT + Codex)

A small, practical kit to help non-technical PMs and TPMs use ChatGPT well
on real program work: meetings, status, Jira, Confluence, SharePoint, risk.

These tools change often. Re-check the setup steps and update "Last updated" whenever you re-run the demo.

## Start here

**If you're a PM or TPM new to this**, do these in order:
1. Read [Quick Reference](quick-reference.md) (5 minutes).
2. Set up a ChatGPT Project for your program using [ChatGPT project instructions](chatgpt-project-instructions.md) (3 minutes).
3. Try three prompts from [Prompt library](prompt-library.md) on your own work: [need to add prompts]
4. Only if you have the ChatGPT desktop app (or the Codex command-line tool) and want more: open [codex-pm-workspace/README.md](codex-pm-workspace/README.md)

**If you're running the training**, read this page to the end, then [demo-script.md](demo-script.md). For the hands-on follow-up, use [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md) (desktop app) or [demo-codex-cli.md](demo-codex-cli.md) (terminal). They cover the same steps, so pick the one your audience will actually use.

## Words you'll see

| Word | What it means |
|---|---|
| **Prompt** | What you type to the AI. |
| **ChatGPT Project** | A folder inside ChatGPT that holds your chats, files, and standing instructions for one program. |
| **Connector** (ChatGPT also calls these "apps") | A link that lets ChatGPT look things up in another tool. We have them for Jira and Confluence. |
| **Codex** | A version of the AI that works directly with a folder of files on your computer. |
| **AGENTS.md** | A plain-English file of standing instructions that Codex reads every time. |
| **Skill** | A saved recipe for a job Codex does often, like a status report. |
| **Hallucination** | When the AI states something false as if it were true. This is why you check names, dates, and numbers. |
| **Markdown** | Plain text with simple formatting marks, like `#` for a heading. Confluence can take it (Insert → Markup → Markdown). Jira can't. |
| **Jira wiki markup** | Jira's own formatting marks, like `h3.` for a heading. Ask the AI for this when the text is going into a ticket. |

## What's in the kit

| File | What it's for | Who uses it |
|---|---|---|
| [demo-script.md](demo-script.md) | Part 1: 45-minute live demo, segment by segment, with exact prompts and an answer key | Presenter |
| [quick-reference.md](quick-reference.md) | Quick reference: the 4-part prompt, getting data in and out, do's and don'ts | Everyone (pin it) |
| [prompt-library.md](prompt-library.md) | 32 copy-and-paste prompts for PM work | Everyone |
| [chatgpt-project-instructions.md](chatgpt-project-instructions.md) | "AGENTS.md for ChatGPT": paste into a ChatGPT Project | Everyone |
| [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md) | Part 2, option A: 20-minute hands-on demo in the ChatGPT desktop app. Opens the workspace folder and runs all five skills on the sample data | Presenter / most people |
| [demo-codex-cli.md](demo-codex-cli.md) | Part 2, option B: the same demo in the Codex command-line tool (terminal) | Presenter / power users |
| [codex-pm-workspace/](codex-pm-workspace/) | Ready-to-use Codex folder: plain-English `AGENTS.md`, 5 skills, sample data | Curious / power users |

### The Codex skills

| Skill | Does |
|---|---|
| `status-report` | Weekly status or exec update from notes and Jira exports |
| `meeting-to-actions` | Decisions, actions, open questions, and a follow-up email |
| `jira-ticket-writer` | Initiative/Epic/Story/Task drafts + CSV for bulk import; Jira export analysis; JQL |
| `raid-log` | Risks, Assumptions, Issues, Dependencies; pre-mortems |
| `explain-it-simply` | Translates technical terms and engineering updates for PMs |

**Sample data** [codex-pm-workspace/inbox/](codex-pm-workspace/inbox/) is a fictional Oracle Health EHR onboarding program with a made-up client:
a weekly sync transcript and a 19-row Jira export with realistic problems built in
(a blocked ticket, stale items, missing owners, a hard compliance deadline). It's safe to use live.

The Jira export is simplified for training. It has one Parent column and joins labels with semicolons.
A real export from our Jira has more columns and may split those up (separate Epic Link and Parent Link columns, several Labels columns).

## Two tracks

- **Track A: everyone (ChatGPT).** Prompt library + quick reference + a ChatGPT Project per program.
  This covers most of what non-technical folks need.
- **Track B: power users (Codex).** The PM Workspace folder. Same rules, but it works over a folder
  of files with saved recipes, so weekly jobs follow the same template.

## Suggested rollout process

| When | What | Owner |
|---|---|---|
| Week 0 | Customize: fill in the ✏️ parts, check with the AI-use policy owner, swap in real Jira conventions | You |
| Week 0 | Pilot: run the demo with 2–3 friendly PMs, then fix whatever confused them | You |
| Week 1 | Team session, Part 1: run [demo-script.md](demo-script.md) (record it) | You |
| Week 2 | Follow-up, Part 2: run [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md) or [demo-codex-cli.md](demo-codex-cli.md) for anyone who wants the hands-on version | You |
| Week 1 | Publish: put the quick reference + prompt library on a Confluence page, **"PM AI Prompt Library"** | You |
| Weeks 2–4 | Homework: each PM uses 3 prompts on real work and shares one win | Each PM |
| Weeks 2–4 | Office hours: 30 minutes, every other week | You |
| Ongoing | "Prompt of the week" in the team channel; people add their own prompts to the Confluence page | Team |
| Week 4 | Quick survey: hours saved per week, top use cases, what's still confusing; report back to the skip-level | You |

## Week-4 survey (5 questions)

1. How often did you use ChatGPT for work in the last two weeks? (Never / 1–2 times / Weekly / Most days)
2. Which tasks did you use it for? (Meetings / Status reports / Jira / Confluence / Documents / Risk / Email / Other)
3. About how much time does it save you in a typical week? (None / Under 1 hour / 1–3 hours / More than 3 hours)
4. What's the most useful thing you've done with it? (free text)
5. What's still confusing, or what's stopping you from using it more? (free text)

## Before you share this

- [ ] Confirm what data is allowed in the company ChatGPT workspace and update the safety lines to match.
- [ ] Fill in the connector steps in [quick-reference.md](quick-reference.md) (two ✏️ spots): how to connect Jira and Confluence, and how to use them in a chat. Confirm whether the connectors can only read, or can also create and edit.
- [ ] Add a demo segment that uses the Jira connector on a real (non-sensitive) project, alongside the CSV version.
- [ ] Check whether there's a SharePoint connector too. The kit assumes there isn't.
- [ ] Fill in the Jira project keys, labels, and required fields in `AGENTS.md` and the Project instructions.
- [ ] Add the ChatGPT desktop app install and access link, and a support contact, to [codex-pm-workspace/README.md](codex-pm-workspace/README.md) (two ✏️ spots).
- [ ] Jira and Confluence are both Data Center (confirmed). Still to check with the Jira admin: whether our Jira has a **Parent Link** field for linking Epics to Initiatives, and whether ticket descriptions use the wiki renderer. Adjust the Jira skill and prompt 3.1 if either differs.
- [ ] Check the exact menu names for Jira export and for Confluence **Insert → Markup → Markdown** on our versions, and correct the quick reference if they differ.
- [ ] Desktop app: during the dry run, find out whether you have to pick a "local" or "this computer" option for the app to work on the folder. Write the exact clicks into [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md).
- [ ] Look at **Work** mode in the ChatGPT desktop app. It can also work with local files, and may suit non-technical people better than Codex mode. The kit doesn't cover it yet.
- [ ] Add the Codex install instructions to [demo-codex-cli.md](demo-codex-cli.md) (one ✏️ spot), and put your name in the Owner row at the top of this page.
- [ ] Set the office hours day and time, and put it in segment 7 of [demo-script.md](demo-script.md) (one ✏️ spot).
- [ ] Try one bulk import of a drafted CSV with the Jira admin, so you know what has to change before it imports.
- [ ] Do a dry run of the demo in ChatGPT (and Codex, if you'll show it) using the sample data, and compare the results to the answer key in the demo script. The kit was written without access to our ChatGPT workspace, so this is the first real test.

## Reference links

- OpenAI: [ChatGPT desktop app](https://learn.chatgpt.com/docs/app)
- OpenAI: [Skills in ChatGPT](https://help.openai.com/en/articles/20001066-skills-in-chatgpt)
