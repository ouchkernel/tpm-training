# Live demo script: "ChatGPT for PMs in 45 minutes"

**Audience:** non-technical PMs and TPMs
**Goal:** everyone leaves able to do 3 things on Monday: turn a meeting into action items, write a status report, and analyze a Jira export.
**Rule for the presenter:** keep the talking short. Most of the session is typing in ChatGPT on a shared screen.

All demo data is fictional and lives in [codex-pm-workspace/inbox/](codex-pm-workspace/inbox/).

---

## Before the session (15 minutes of prep)

- [ ] Log into the **company** ChatGPT workspace. Close personal tabs.
- [ ] Have these files on your desktop: [codex-pm-workspace/inbox/weekly-sync-transcript.txt](codex-pm-workspace/inbox/weekly-sync-transcript.txt), [codex-pm-workspace/inbox/jira-export-ehr-onboarding.csv](codex-pm-workspace/inbox/jira-export-ehr-onboarding.csv).
- [ ] Create an empty ChatGPT Project called **"Oracle Health EHR Onboarding (demo)"**. Don't add instructions yet.
- [ ] Open `03-prompt-library.md` in another window for copy and paste.
- [ ] Optional (for segment 6): open the [codex-pm-workspace](codex-pm-workspace/) folder in the ChatGPT desktop app, with the selector set to Codex, and confirm it lists the 5 skills.
- [ ] The sample Jira export is simplified for training: one Parent column, and labels joined with semicolons. A real export from our Jira will have more columns and may split these up. Say so if someone asks.
- [ ] The sample data is frozen in time. Whenever a prompt asks for today's date, use **November 16, 2026**, no matter when you run the demo. Otherwise every ticket looks overdue.
- [ ] Do one dry run. AI output changes every time, so know roughly what to expect, not the exact words. Check the results against the **answer key** at the end of this script.
- [ ] **Backup plan:** run every prompt once beforehand and save screenshots. If the live demo stalls, show those.

---

## Segment 1: Why, and the rules (0:00–0:05)

**Say:**
- "ChatGPT gets you most of a first draft in 2 minutes. You used to spend 30."
- "It's like a sharp new hire on day one. Fast. Knows nothing about our programs. And it will guess if you let it."

**Show the 3 rules** (from [quick-reference.md](quick-reference.md)):
1. Company workspace only. Follow the AI-use policy. No patient data, no passwords.
2. You own the output. Check every name, date, and number.
3. Give it context. A vague ask gets a vague answer.

---

## Segment 2: Bad prompt vs. good prompt (0:05–0:13)

**This is the part people remember. Don't rush it.**

**Step 1.** In a new chat, attach [codex-pm-workspace/inbox/weekly-sync-transcript.txt](codex-pm-workspace/inbox/weekly-sync-transcript.txt) and type:
```
Summarize this.
```
**Point out:** the summary may read fine. Ask the room what they'd still have to do before sending it. Usually: pull out who owns what, find the dates, and work out what's missing. The prompt didn't ask for any of that, so you got a guess at what you wanted.

**Step 2.** New chat, same file, then paste prompt **1.1** from the prompt library (Notes → action items).

**Point out:**
- Decisions, actions, owners, and dates now sit in a clean table.
- Look for `[NEEDS INPUT]`: Marcus has to confirm who covers for him, but nobody gave a date. The due date is flagged, not invented.
- "Same file, same tool. The only difference is the prompt."

**Step 3.** Show the 4-part formula: **Goal, Context, Source, Format**. Map each part back to the prompt you just used.

---

## Segment 3: One meeting, four outputs (0:13–0:22)

Stay in the same chat as Step 2. Show how **follow-up prompts build on each other**.

1. **Follow-up email:** paste prompt **1.2**.
   *Point out:* each action starts with the owner's name, it's short, and it's ready to send after a quick check.
2. **Risks:** type:
   ```
   What are the biggest risks to the January 26 go-live from this meeting? Rank them.
   ```
   *Expect:* the Dec 15 security board date, the contractor SSO dependency, the network ranges due Nov 24, the data-cleanup question, and the infrastructure coverage gap over the holidays.
3. **Jira tickets:** paste prompt **3.1** and add: "Only create tickets for the action items above."
   *Point out:* most of these come out as Tasks, each with checkable acceptance criteria, plus a CSV you can take to the Jira admin for bulk import.
4. **Revise, don't restart:** type:
   ```
   Make the email shorter and warmer. Tom is the client. Thank him for owning the network ranges.
   ```
   *Point out:* "You just edited by talking. You don't need to start over."

---

## Segment 4: Analyze a Jira export (0:22–0:30)

1. New chat. Attach [codex-pm-workspace/inbox/jira-export-ehr-onboarding.csv](codex-pm-workspace/inbox/jira-export-ehr-onboarding.csv). Paste prompt **3.4**, and for the date type **November 16, 2026**.
2. *Point out:*
   - Blocked: **EHR-13** (firewall rules, waiting on the client).
   - Stale: EHR-13 hasn't been touched in about a month. EHR-23 and EHR-52 have no owner and no due date.
   - Overdue: **EHR-43** (second test load, due Nov 13). Bug **EHR-42** has no due date.
   - "This takes 15 minutes by hand every Monday."
   - **EHR-32** is a ticket for the architecture diagram. In the last segment, ChatGPT almost certainly drafted a new ticket for that same action, because it had no export to check against. "It already existed. Check the export before you create tickets."
3. **JQL for non-technical people:** paste prompt **3.5** with:
   *"everything in project EHR that's blocked or has no assignee, sorted by priority"*.
   *Point out:* "You don't have to memorize JQL. Ask, paste it into Jira's advanced search, and check that the results look right."
4. **Set up the next segment.** Say: "For a status report I need this Jira export *and* the meeting transcript, which is in a different chat. I could re-attach everything and re-explain our rules every time. Or I can set it up once." That leads into segment 5.

---

## Segment 5: Set it up once with a ChatGPT Project (0:30–0:37)

1. Open the **"Oracle Health EHR Onboarding (demo)"** Project.
2. Paste the instructions from `04-chatgpt-project-instructions.md` into the Project's instructions. Fill in the ✏️ lines with demo values first: program "Oracle Health EHR Onboarding", Jira project key "EHR". Do this before the session to save time, and just show the result.
3. Upload both sample files to the Project.
4. Start a new chat in the Project and type only:
   ```
   Write the status report for November 9 to 16, 2026.
   ```
5. *Point out:* the report combines both files. A good result notices that the firewall ticket (EHR-13) is due Nov 20, but the client said the network ranges won't arrive until Nov 24. No one said that out loud in the meeting. If it doesn't catch this, ask: "Do any Jira due dates conflict with what was said in the meeting?"
6. *Point out:* it now knows our Jira structure, what Green/Yellow/Red mean, to mark gaps, and where the files are. "You set this up once per program, and every chat after that starts smart."

---

## Segment 6 (optional, for the curious): Codex and the PM Workspace (0:37–0:41)

Skip this segment if the room is mostly brand new. Offer it as a follow-up session instead.
This is only a teaser. The full 20-minute walkthrough of all five skills is in [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md) (desktop app) or [demo-chatgpt-desktop.md](demo-chatgpt-desktop.md) (terminal).

1. Show the folder: `inbox/` → `outputs/`, plus `AGENTS.md`.
2. Open `AGENTS.md`. "This is the same idea as Project instructions, just in a file. It's plain English. You edit the parts with the pencil."
3. In the ChatGPT desktop app (folder open, selector on Codex), type:
   ```
   Make the status report for November 9 to 16, 2026 from the files in inbox.
   ```
4. Show the new file in `outputs/`.
   *Point out:* "It used the saved status-report recipe (a 'skill'), so the layout stays consistent from week to week."

---

## Segment 7: Homework and next steps (0:41–0:45)

**This week, try three things on your own real work** (following the policy):
1. Turn one meeting into action items (prompt 1.1).
2. Write your status report with ChatGPT (prompt 2.1).
3. Run your Jira export through prompt 3.4.

**Then:**
- Set up a ChatGPT Project for your main program.
- Post your best prompt on the team Confluence page **"PM AI Prompt Library"**.
- Bring questions to office hours: ✏️ _[day and time]_.

**Close with:** "Pick the weekly chore you like least and start there."

---

## Questions you'll probably get

| Question | Answer |
|---|---|
| "Is it safe to paste client info?" | Follow the company AI-use policy and use only the company workspace. When in doubt, leave it out or anonymize it ("Client A"). |
| "It gave me a wrong date." | That's why rule #2 exists. Ask "Where did that come from?" and remind it to use only your source. |
| "Can it update Jira directly?" | Not by default. Draft in ChatGPT, then paste into Jira or bulk-import the CSV. With the Jira connector it can look tickets up. Whether it can change them depends on how our admins set the connector up. |
| "Does it remember me?" | Inside a Project, it always uses the Project's instructions and files. ChatGPT may also have a Memory feature turned on that carries some things between chats, but don't rely on it for work. Put what matters in the Project or in your prompt. |
| "ChatGPT or Codex?" | ChatGPT for most things. Codex when you're working with a folder of files or want a repeatable recipe. |

---

## Answer key (for the presenter's dry run)

Use this to check that the AI's output is right. Wording will vary. The facts should not.

### The meeting transcript

**Decisions (3)**
1. Target go-live stays January 26.
2. Go-live readiness review is January 12.
3. SSO for contractors is in scope for go-live.

**Action items (6)**

| Action | Owner | Due |
|---|---|---|
| Send final network ranges to Marcus | Tom | Nov 24 |
| Introduce Priya to Rachel (IAM team) | Tom | Same day as the meeting (Nov 10) |
| Deliver final architecture diagram to Elena | Marcus | Dec 1 |
| Submit security package to the state | Elena | Dec 8 |
| Find out if the client can supply a cleaned data extract | Tom | Friday (Nov 13). He said "I'll try." |
| Confirm who covers infrastructure Dec 18 to Jan 4 | Marcus | Not stated → should be `[NEEDS INPUT]` |

**Open questions:** Can the client supply a cleaned extract (if not, about 2 extra weeks)? Who covers for Marcus?

**Top risks:** the Dec 15 review board (miss it and go-live slips to after mid-January); network ranges after Nov 24 push production a week; contractor SSO depends on a new client contact; 4% of records failed validation; infrastructure coverage over the holidays.

### The Jira export (with "today" = November 16, 2026)

| Check | Expected |
|---|---|
| Total tickets | 19 |
| By status | To Do 8, In Progress 7, Done 3, Blocked 1 |
| Blocked | EHR-13 |
| Overdue (not Done) | EHR-43 (due Nov 13) |
| Not updated in 14+ days (not Done) | EHR-12, EHR-13, EHR-22, EHR-23, EHR-43, EHR-50, EHR-51, EHR-52 |
| No assignee | EHR-23, EHR-52 |
| No due date | EHR-23, EHR-42, EHR-52 |
| Cross-check with the meeting | EHR-13 is due Nov 20, but the network ranges it needs arrive Nov 24 |

If the AI's counts don't match, say so in the room: "This is why we check."

### The JQL query (segment 4)

For "everything in project EHR that's blocked or has no assignee, sorted by priority", expect something close to:

`project = EHR AND (status = Blocked OR assignee is EMPTY) ORDER BY priority DESC`

### Ticket drafts (hands-on demos, step 3)

| Meeting action | Expected |
|---|---|
| Architecture diagram by Dec 1 | Already in Jira as EHR-32. Should not be drafted again. |
| Submit security package by Dec 8 | Already in Jira as EHR-31. Should not be drafted again. |
| Network ranges by Nov 24 | Covered by EHR-13 (firewall rules, blocked on the client). An update to that ticket, not a new one. |
| Intro to the client's IAM contact | New Task, or a note on EHR-22. Either is fine. |
| Find out about a cleaned data extract | New Task, or a note on EHR-42. Either is fine. |
| Confirm infrastructure coverage for Dec 18 to Jan 4 | New Task. No due date was given. |

The check that matters: it must not re-create EHR-32 or EHR-31.

### RAID log (hands-on demos, step 4)

Wording and ratings will vary. These items should all be there:

- **Risks:** missing the Dec 15 review board; network ranges arriving after Nov 24; no infrastructure cover from Dec 18 to Jan 4.
- **Assumptions:** the client can supply a cleaned data extract.
- **Issues:** contractor SSO not working; firewall rules blocked (EHR-13); 4% of records failed validation.
- **Dependencies:** network ranges from the client; a client IAM contact for the contractor directory; the architecture diagram, needed by Dec 1 for the security package.

### Status report (segment 5, and hands-on step 5)

- **Overall status:** Yellow is the call that fits. There's a hard Dec 15 date with open dependencies, and a plan to hit it. If it says Green, ask it to explain that against the Dec 15 date.
- **Reporting period:** November 9 to 16, 2026, stated at the top.
- **Progress:** there isn't much that happened inside November 9 to 16, and a good report says so.
  - Inside the period: the Nov 10 decisions (go-live held at Jan 26, readiness review set for Jan 12, contractor SSO confirmed in scope), the security plan reported at about 70%, Tom agreeing to own the network ranges, and EHR-32 created for the architecture diagram.
  - Before the period: the non-prod environment passed its checks on Nov 5, and Jira shows staff SSO (EHR-21) and the first test load (EHR-41) done in early November. A careful report leaves these out of "Progress this period" or labels them as earlier work. If it lists them as this period's progress, that's a good catch to point out.
  - No tickets were closed inside the period, so it should not claim any were.
- **Decisions or help needed:** at least the client-side items (network ranges, data extract).
- **Revised version:** shorter, aimed at a director, saved as a second file.
