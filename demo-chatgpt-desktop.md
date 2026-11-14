# Hands-on demo: the PM Workspace and its skills in the ChatGPT desktop app

Run this as a separate follow-up to the main session in `01-demo-script.md`. If you fold it into the main session instead, drop that script's segment 6 and plan for about an hour in total.

All sample data is fictional. Wherever a date is needed, use **November 16, 2026**.

---

## Before you start (5 minutes of prep)

- [ ] Install the ChatGPT desktop app and sign in with your **company** account.
- [ ] Copy the `codex-pm-workspace` folder somewhere easy to find, like Documents.
- [ ] In the app, choose to **open a folder** and pick `codex-pm-workspace`. The app will ask for permission to read and change files in that folder. Approve it.
- [ ] Above the message box, set the selector to **Codex** (not plain ChatGPT). This should be the mode that reads `AGENTS.md` and the skills in the folder. Step 1 confirms it.
- [ ] Run step 1 below as your check. If it lists the instructions and the five skills, you're set.
- [ ] Confirm `inbox/` has the two sample files: `weekly-sync-transcript.txt` and `jira-export-ehr-onboarding.csv`.
- [ ] Empty the `outputs/` folder so new files are easy to spot.
- [ ] Keep the folder open in Finder / File Explorer next to the app, so people can watch files appear.
- [ ] Do one dry run. Compare the results with the answer key in `demo-script.md`.

---

## Step 1: The 60-second tour (0:00–0:02)

Show the folder and say:

- "`inbox/` is where I put my files. `outputs/` is where the app saves its work."
- "`AGENTS.md` is a page of standing instructions in plain English. The app reads it every time."
- "Skills are saved recipes for jobs I do every week. There are five."

Then, in a new chat in the folder, type:
```
What are your instructions, and what skills do you have?
```
**Point out:** it describes the rules from `AGENTS.md` and lists the five skills. "It's set up. I didn't configure anything."

---

## Step 2: Meeting → actions (0:02–0:06)

Type:
```
Today is November 16, 2026. Turn weekly-sync-transcript.txt into action items and a follow-up email.
```

**What happens:** the app picks the `meeting-to-actions` skill on its own and saves a file like `outputs/2026-11-16-meeting-recap-weekly-sync.md`.

**Open the file and point out:**
- 3 decisions, 6 action items in a table, and open questions.
- Marcus's "confirm who covers for me" action has `[NEEDS INPUT: due date]`. Nobody said a date, so it didn't invent one.
- A draft follow-up email at the bottom, in plain text so it pastes cleanly into Outlook.
- "I didn't say which skill to use. I asked in plain English and it matched the request to the recipe."

---

## Step 3: Jira export → what to chase (0:06–0:10)

Type:
```
Look at jira-export-ehr-onboarding.csv. Today is November 16, 2026. What should I chase this week?
```

**What happens:** the `jira-ticket-writer` skill analyzes the export and saves a report to `outputs/`.

**Point out:**
- Counts by status: To Do 8, In Progress 7, Done 3, Blocked 1.
- Blocked: EHR-13. Overdue: EHR-43. No owner: EHR-23 and EHR-52.
- A short "chase this week" list with a reason for each.

**Then draft new tickets.** Type:
```
Draft Jira tickets for the action items from the meeting recap you just made. Check the Jira export first and skip anything that already has a ticket.
```
**Point out:**
- An "Already in Jira" list. The architecture diagram is EHR-32 and the security plan is EHR-31, so it should not draft those again. The network ranges belong on EHR-13 as an update. "Always check what exists before you create tickets."
- A few new tickets for the rest, each with a summary, description, and checkable acceptance criteria.
- The descriptions are in Jira's own formatting, ready to paste into a ticket.
- A CSV draft to take to the Jira admin. It is a starting point, not something to import as-is.

---

## Step 4: RAID log, calling a skill by name (0:10–0:13)

Type:
```
$raid-log use both files in inbox. Today is November 16, 2026.
```

**Say:** "The dollar sign calls a skill by name. Use it when you want to be sure which recipe runs."
(If the dollar sign doesn't bring up the skill in your version of the app, type: *"Use the raid-log skill on both files in inbox."*)

**Point out in the output:**
- **Risk:** the state review board meets Dec 15. Miss it and go-live slips.
- **Assumption:** the client can supply a cleaned data extract. Sam literally said "I'm assuming."
- **Issue:** contractor SSO doesn't work yet; firewall rules are blocked.
- **Dependency:** network ranges from the client by Nov 24.
- Owners it couldn't find are marked `[NEEDS INPUT: owner]`.
- "Top 3 to raise with leadership" at the bottom.

---

## Step 5: Status report (0:13–0:16)

Type:
```
Make the status report for November 9 to 16, 2026 from the files in inbox.
```

**Point out:**
- The reporting period is stated at the top.
- One page, in our standard layout, with a Green / Yellow / Red call and the reason.
- It lists the files it used at the bottom.
- "The skill hands it the same template each time, so the layout stays consistent from week to week. I still read every report before it goes out."

**Now revise it. Don't start over.** Type:
```
My director is the audience. Cut it to the summary, top 3 risks, and decisions needed.
```
**Point out:** it should save a `-v2` file and leave the first one alone. Look in the folder to confirm.

---

## Step 6: Explain it simply (0:16–0:18)

Type:
```
In the transcript, Priya says SSO works for staff but not contractors because they're in a separate directory. What does that mean, and what should I ask her?
```

**Point out:**
- A one-sentence explanation, an everyday comparison, and why it matters for the go-live date.
- Three questions to take back to the engineer.
- "This is how you get ready for a technical meeting in two minutes."

---

## Step 7: Wrap up (0:18–0:20)

Show the `outputs/` folder. There should be seven new files from 15 minutes of work: the meeting recap, the Jira analysis, the ticket drafts (two files), the RAID log, and two versions of the status report.

**Say:**
- "On Monday, do the same thing with your own files: drop them in `inbox/`, ask, check, revise."
- "Everything it wrote is a draft. I still check every name, date, and number before it goes anywhere."
- "To make it yours, open `AGENTS.md` and fill in the pencil-marked lines."

---

## If something goes wrong

| What you see | What to do |
|---|---|
| The app asks permission to read a file, run a command that reads or counts files in this folder, or save to `outputs/` | Approve it. That's normal. |
| The app asks to install something or use the internet | Say no, and ask it to work with the files as they are. |
| A chat seems stuck | It's probably waiting for you to approve something. Look for a prompt. |
| It doesn't list the skills in step 1 | Check two things: the selector is on **Codex**, and you opened `codex-pm-workspace` itself, not the folder above it. |
| It doesn't know about `AGENTS.md` | Same two checks. Then start a new chat in the folder. |
| It used the wrong skill | Call the one you want by name, like `$status-report`. |
| The numbers don't match the answer key | Say so out loud: "This is why we check." Then ask it: "Recount the tickets by status and show me the list." |
| The output is too long or off-target | Tell it what to change. Don't start a new chat. |

---

## Prefer the terminal?

The same demo for the Codex command-line tool is in `demo-codex-cli.md`.
