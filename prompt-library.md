# PM / TPM Prompt Library for ChatGPT

Copy a prompt, replace the capitalized **[BRACKETS]** (like `[MEETING NAME]` or `[DATE]`), attach or paste your source, and send.
Leave `[NEEDS INPUT]` exactly as it is. That one is an instruction to ChatGPT, not a blank for you.
Every prompt works in ChatGPT. Most also work in Codex (put the file in `inbox/` and name it).

> **Before you paste anything:** follow the company AI-use policy. Use only the company ChatGPT workspace.
> No patient data, no passwords, nothing a client would be upset to see. If you're unsure, leave it out.

---

## How to write a good prompt (the 4 parts)

| Part | Ask yourself | Example |
|---|---|---|
| **Goal** | What do I want, and who is it for? | "Write a status update for my director…" |
| **Context** | What would a new teammate need to know? | "…for a state client onboarding. Go-live is Jan 26. Security review is the big risk…" |
| **Source** | What should it work from? | "…using the meeting notes I've attached…" |
| **Format** | What should it look like? | "…as 5 bullets, under 120 words, risks first." |

**Three phrases worth adding to almost any prompt:**
- *"Ask me up to 3 questions before you start."*
- *"Don't make anything up. Mark gaps as [NEEDS INPUT]."*
- *"Now critique your answer as a skeptical director, then improve it."*

---

## 1. Meetings

### 1.1 Notes or transcript → action items
```
Here are my notes / transcript from [MEETING NAME] on [DATE].
Pull out:
1. Decisions made
2. Action items as a table: Action | Owner | Due date
3. Open questions
4. Risks that were raised
Only list an owner or date if someone actually said it. Otherwise write [NEEDS INPUT].

[PASTE OR ATTACH NOTES]
```

### 1.2 Follow-up email
```
Using the action items above, write a follow-up email to the attendees.
Under 200 words. Friendly, direct. Plain text, ready to paste into Outlook.
Start each action item with the owner's name so people can spot their items.
End by asking people to reply if I missed anything.
```

### 1.3 Meeting prep
```
I'm running a [LENGTH, e.g. 30]-minute meeting with [WHO] about [TOPIC].
The outcome I need is: [DECISION OR RESULT].
Draft an agenda with time boxes, the 3 questions I must get answered,
and the pushback I should expect, with a one-line response to each.
```

### 1.4 Prep for a meeting I'm nervous about
```
Act as [ROLE, e.g. "the client's IT director, who is frustrated about delays"].
I'll tell you about [SITUATION]. Push back the way they would.
After 5 exchanges, stop and give me feedback on how I handled it.
```

---

## 2. Status and reporting

### 2.1 Weekly status report
```
Write a status report for [PROGRAM] for [AUDIENCE, e.g. my director].
Reporting period: [START DATE] to [END DATE].
Use this format:
- Reporting period
- Overall status: Green / Yellow / Red, with one sentence on why
- Summary (3 bullets)
- Progress this period (only what my sources show happened in the period)
- Coming up next
- Risks and issues (table: Risk / issue | Impact | Owner | What we're doing about it)
- Decisions or help needed
- Key dates (table: Milestone | Target date | Status)
- Sources used
Green = on track. Yellow = at risk but we have a plan. Red = need leadership help.
Don't soften bad news. Mark anything missing as [NEEDS INPUT].

Source material:
[PASTE NOTES, JIRA EXPORT, OR LAST WEEK'S REPORT + WHAT CHANGED]
```

### 2.2 Executive summary
```
Turn this into a 5-line summary for a VP who will read it on their phone.
Line 1: overall status and the single most important thing.
Lines 2–4: what changed, the biggest risk, what we need.
Line 5: next milestone and date.

[PASTE REPORT]
```

### 2.3 Same update, three audiences
```
Rewrite this update three ways:
1. For engineers (specific, technical details OK)
2. For my director (risks, dates, decisions)
3. For the client sponsor (progress, what we need from them, no internal names)

[PASTE UPDATE]
```

### 2.4 Explain why we're Yellow / Red
```
We're [YELLOW/RED] on [PROGRAM] because [REASON].
Write a short, calm explanation for leadership that covers:
what happened, the impact on dates, what we're doing about it, and what we need from them.
No blame. Under 150 words.
```

---

## 3. Jira

> **Tip:** Our issue types are **Initiative → Epic → Story / Task**, plus **Bug**.
> To give ChatGPT real data, use the **Jira connector** and ask about tickets directly
> (see "Getting data out of our tools" in the quick reference), or run your Jira search → **Export → CSV** and attach the file.
>
> **Our Jira is Data Center, and it doesn't read Markdown.** When you want text to paste into a ticket, add this line to your prompt:
> *"Format it in Jira wiki markup."*

### 3.1 Break work into tickets
```
Break this work into Jira tickets using our structure:
Initiative → Epics → Stories and Tasks.
- Story = something a user or client needs. Format: "As a [who], I want [what] so that [why]."
- Task = work to be done that isn't a user need.
For each ticket give: Issue type, Summary (starts with a verb, under 80 characters),
Description (2–4 sentences), Acceptance criteria (bullet list), and which Epic or Initiative it belongs to.
Format the descriptions and acceptance criteria in Jira wiki markup.
If I've attached a Jira export, check it first. Don't draft tickets for work that already
has one. List those separately with their ticket keys.
Then give the new tickets again as a CSV with columns:
Issue Type, Summary, Description, Acceptance Criteria, Epic Name, Epic Link, Parent Link.
(Epic Name is for Epics. Epic Link is the Epic a Story or Task belongs to.
Parent Link is the Initiative an Epic belongs to. I'll check the CSV with our Jira admin
before any bulk import.)

The work: [DESCRIBE OR PASTE NOTES / REQUIREMENTS]
```

### 3.2 Write acceptance criteria
```
Write acceptance criteria for this Jira story. Each one must be something
you can check as yes or no. Include at least one "what if it goes wrong" case.

Story: [PASTE STORY]
```

### 3.3 Clean up a messy ticket
```
Rewrite this Jira ticket so someone who wasn't in the meeting can pick it up.
Clear summary, short description, acceptance criteria, and list any open questions.
If it's really two or more tickets, split it.

[PASTE TICKET]
```

### 3.4 Analyze a Jira export
```
Attached is a Jira CSV export for [PROGRAM]. Today is [DATE]. Tell me:
1. Counts by status and by assignee
2. Anything Blocked, overdue (due date has passed and the ticket is not Done), or not updated in 14+ days (ignore Done tickets)
3. Tickets with no assignee or no due date
4. The 5 things I should chase this week, and why
Put the results in tables. Don't guess at anything that isn't in the file.
```

### 3.5 Write a Jira search for me (JQL)
```
Write a Jira JQL query that finds: [DESCRIBE IN PLAIN ENGLISH,
e.g. "everything in project EHR that's blocked, or past its due date and not Done, sorted by due date"].
Explain each part of the query in one line of plain English.
```

---

## 4. Confluence

> **Tip:** With the **Confluence connector**, ChatGPT can find and read existing pages for you.
> This kit assumes you publish by pasting the result into Confluence yourself. Whether the connector can create or edit pages hasn't been confirmed.
>
> **To add a page:** copy the Markdown, then in the Confluence editor choose **Insert → Markup**, pick **Markdown**, and paste.

### 4.1 Notes → Confluence page
```
Turn these rough notes into a Confluence page.
Start with a 3–5 line summary. Then use short sections with headings.
Use tables for owners, dates, and status. Give it to me as Markdown in a code block.

Page title: [TITLE]
Notes: [PASTE]
```

### 4.2 Program one-pager / charter
```
Draft a one-page program charter for [PROGRAM] with these sections:
Purpose, Scope (in / out), Key milestones, Stakeholders and roles (table),
Success criteria, Top risks, How we communicate (meetings, reports, channels).
Use [NEEDS INPUT] wherever I haven't given you the facts.

What I know so far: [PASTE]
```

### 4.3 How-to / process page
```
Write a step-by-step Confluence how-to for [PROCESS, e.g. "requesting a new environment"].
Audience: [WHO]. Number the steps. Add a "Before you start" box and a
"Who to contact if you're stuck" section. Ask me questions if any step is unclear.
```

### 4.4 RACI chart
```
Make a RACI chart (Responsible, Accountable, Consulted, Informed) for [PROGRAM / PROCESS].
Roles: [LIST ROLES]. Activities: [LIST, or ask ChatGPT to suggest them].
Exactly one "A" per activity. Flag any activity with no "R".
```

---

## 5. SharePoint and documents

> **Tip:** Download the file from SharePoint and attach it.

### 5.1 Summarize a long document
```
Summarize the attached document for a busy program manager:
- What it is and why it matters (2 sentences)
- Key points (5 bullets max)
- Anything that affects our dates, costs, or responsibilities
- Questions I should ask the author
Note the page or section for each key point.
```

### 5.2 Contract / SOW → checklist
```
Read the attached [SOW / contract / requirements doc] and pull out every deliverable,
deadline, and obligation, for us AND for the client.
Table: Item | Who owns it | Due / trigger | Section reference.
Flag anything vague that could cause a dispute later.
```

### 5.3 Compare two versions
```
Compare these two versions of [DOCUMENT]. List what was added, removed, or changed
that would matter to the program: scope, dates, responsibilities, costs.
Ignore wording and formatting changes.
```

---

## 6. Planning and risk

### 6.1 RAID log
```
From the material below, build a RAID log:
Risks, Assumptions, Issues, Dependencies.
Table: ID | Type | Description | Likelihood (H/M/L) | Impact (H/M/L) | Owner | Next step.
Sort most severe first. Then list the top 3 to raise with leadership.

[PASTE NOTES / STATUS / PLAN]
```

### 6.2 Pre-mortem
```
Imagine it's [TIMEFRAME, e.g. 6 months] from now and [PROGRAM] failed or missed go-live badly.
List the 10 most likely reasons it happened, based on what I've told you.
For each, give an early warning sign and one thing I can do now to prevent it.

Context: [PASTE]
```

### 6.3 Milestone plan
```
I need to get from [START STATE] to [END STATE] by [DATE].
Draft a milestone plan working backward from that date.
Show dependencies between milestones and call out the critical path.
Tell me which dates look unrealistic and why.
```

### 6.4 Client onboarding checklist
```
Build a checklist for onboarding a new [state / federal] client onto our cloud EHR.
Group it by phase: kickoff, environment build, identity and access, security authorization,
data migration, testing, training, go-live, after go-live.
For each item: what it is, who usually owns it (us / client / both), and what "done" looks like.
Mark items you're unsure about so I can check them with the team.
```

### 6.5 Stress-test my plan
```
Here's my plan for [WHAT]. Act as a skeptical senior program director.
Find the 5 weakest points: missing steps, unrealistic dates, unclear owners, hidden dependencies.
Be blunt. Then suggest a fix for each.

[PASTE PLAN]
```

---

## 7. Communication

### 7.1 Deliver bad news
```
I need to tell [WHO] that [BAD NEWS, e.g. "go-live will slip 2 weeks"].
Reason: [WHY]. What we're doing: [PLAN]. What I need from them: [ASK].
Write a short email that's honest, calm, and doesn't blame anyone.
Give me two versions: one more formal, one more conversational.
```

### 7.2 Escalation
```
Draft an escalation to [LEADER] about [ISSUE].
Structure: the problem in one sentence, impact (dates, cost, client), what we've tried,
options with pros and cons, my recommendation, and the decision I need by [DATE].
Under 200 words.
```

### 7.3 Reply to a difficult email
```
Help me reply to this email. My goal is [GOAL, e.g. "hold the date without damaging the relationship"].
Keep it professional and short. Point out anything in their email I should NOT respond to.

[PASTE EMAIL]
```

### 7.4 Teams message
```
Turn this into a Teams message to [PERSON / CHANNEL]: 3 short lines max,
a clear ask, and a deadline.

[PASTE WHAT YOU WANT TO SAY]
```

---

## 8. Learning the technical side

### 8.1 Explain it simply
```
Explain [TERM / CONCEPT] to me. I'm a program manager, not an engineer.
Give me: a one-sentence definition, why it matters for my program,
an everyday comparison, and 3 smart questions I could ask the engineers.
```

### 8.2 Decode an engineering update
```
An engineer sent me this update. Translate it into plain English.
What does it mean for my dates and risks? What should I ask next?

[PASTE UPDATE]
```

### 8.3 Learn a topic in a week
```
I need to understand [TOPIC, e.g. "FedRAMP authorization"] well enough to run meetings about it.
Give me a 5-day plan, 20 minutes a day. Each day: what to learn, a simple explanation,
and a 3-question quiz. Start with Day 1 now.
```

---

## 9. Fix-it phrases (when the answer isn't right)

| Problem | Say this |
|---|---|
| Too long | "Cut this in half. Keep only what a director needs." |
| Too vague | "Be specific. Use the names, dates, and numbers from my notes." |
| Wrong tone | "Make it warmer / more direct / less salesy." |
| Sounds like AI wrote it | "Rewrite this in plain, direct language. Mix short and long sentences. Cut filler like 'furthermore,' 'robust,' and 'it's important to remember.'" |
| Made something up | "Where did [X] come from? Only use what I gave you." |
| Not sure it's right | "What assumptions did you make? What might be wrong?" |
| Want options | "Give me 3 different versions and tell me when I'd use each one." |
| Starting over | Don't. Say what's wrong and ask it to revise. |
