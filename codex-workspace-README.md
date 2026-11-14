# PM Workspace for Codex: setup in 5 minutes

This folder is a ready-made "office" for Codex. You put your files in `inbox/`,
ask in plain English, and Codex saves the results in `outputs/`.

```
codex-pm-workspace/
├── AGENTS.md          ← Codex's standing orders (edit the ✏️ parts once)
├── inbox/             ← Put your files here (notes, Jira CSVs, docs)
├── outputs/           ← Codex saves its work here
└── .agents/skills/    ← Saved "recipes" for common jobs (hidden folder)
```

> **Can't see `.agents`?** Folders that start with a dot are hidden.
> On a Mac, press **Cmd + Shift + .** in Finder to show them. On Windows, in File Explorer choose **View → Show → Hidden items**. You don't need to open it.
> It just has to be there.

## Before you start

You need the **ChatGPT desktop app** (Mac or Windows) signed in with your **company** account. It has Codex built in, so you don't need a terminal.
✏️ _[Kit owner: add the link to our install and access instructions here.]_
If you don't have the desktop app yet, skip this folder for now. The ChatGPT files in the kit cover most of what you need.

## One-time setup

1. **Copy this whole folder** somewhere easy to find, like your Documents folder. Keep one folder per program if you like (e.g. `ehr-onboarding-pm-workspace`).
2. **Open `AGENTS.md`** in any text editor and fill in the ✏️ parts: your name, your program, your stakeholders, and your Jira project key.
3. **Open the folder in the ChatGPT desktop app.**
   - Choose to **open a folder** and pick this one. Approve the request to read and change files in it.
   - Above the message box, set the selector to **Codex**.
   - *Prefer the terminal?* Type `cd ` (with a space), drag the folder onto the Terminal window, press Enter, then type `codex` and press Enter. This needs the Codex command-line tool installed.
4. **Check that it worked.** Ask: *"What are your instructions, and what skills do you have?"*
   Codex should describe your AGENTS.md and list the five skills.

> **Want to see it in action first?** `[demo-chatgpt-desktop.md](demo-chatgpt-desktop.md)demo-chatgpt-desktop.md` in the kit (or `[demo-codex-cli.md](demo-codex-cli.md)` for the terminal) walks through all five skills on the sample files, step by step. You can follow it on your own.

## Everyday use

1. Download what you need from Jira, Confluence, SharePoint, or Teams into `inbox/`.
   - **Jira:** run your search or filter → **Export** → **CSV**.
   - **Confluence:** copy the page text and paste it into a `.txt` file. (Word and PDF exports can work too, but plain text is the most reliable.)
   - **Teams meeting:** download the transcript. Pick the `.vtt` option if you're offered one, because it's plain text.
   - **Rule of thumb:** `.txt`, `.csv`, and `.md` files always work. If Codex says it can't read a Word, PDF, or Excel file, re-save it as text or CSV.
2. Ask Codex in plain English. For example:
   - *"Make the status report for November 9 to 16 from the files in inbox."* (Give the dates you're reporting on.)
   - *"Turn `weekly-sync-transcript.txt` into action items and a follow-up email."*
   - *"Look at the Jira export and tell me what I should chase this week."*
   - *"Draft Jira stories for the identity setup work in the meeting notes."*
   - *"What does 'SAML federation' mean, and what should I ask the engineers?"*
3. Open the file in `outputs/`, review it, and fix anything marked `[NEEDS INPUT]`.
4. Move it where it needs to go:
   - **Confluence:** edit the page, choose **Insert → Markup**, pick **Markdown**, and paste.
   - **Jira:** ticket drafts come with the description already in Jira's own formatting. Copy that block into the ticket.
   - **Email or Teams:** ask for a plain-text version (*"give me that as plain text for an email"*), so you don't get stray `#` and `*` marks.

## When Codex asks for permission

Codex sometimes stops and asks before it does something, like running a command.
- Reading files in this folder, running a command that reads or counts them, and saving to `outputs/` are normal. Approve those.
- If it wants to install something, use the internet, or touch files outside this folder,
  say **no** and ask it why. If you're unsure, ask ✏️ _[kit owner / support contact]_.

## Good habits

- **Edit what it gives you.** Check names, dates, and numbers before you send anything.
- **Start a fresh session for each new task.** It keeps Codex focused.
- **If the result is off, say why.** For example: *"Too long. Cut it to 5 bullets for my director."* Don't start over.
- **Keep sensitive data out.** Follow the company AI-use policy. No patient data, no passwords. If you're unsure, leave it out.

## Starting a second program

Copy this **whole folder** and rename the copy. Don't copy the skills on their own.
They rely on this folder's `AGENTS.md` (status colors, file naming, the rules) and on the `inbox/` and `outputs/` folders being there.
