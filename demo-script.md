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
