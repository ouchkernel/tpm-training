# ChatGPT for PMs: quick reference

## The 4-part prompt

**Goal** (what + who it's for) → **Context** (what a new teammate would need to know) → **Source** (attach or paste the material) → **Format** (length, structure, tone)

> **Weak:** *"Write a status update."*
>
> **Better:** *"Write a status update for my director on the Oracle Health EHR onboarding. We're Yellow because the state security board's next meeting is Dec 15. Use the attached meeting notes. 5 bullets, under 120 words, risks first. Mark anything missing as [NEEDS INPUT]."*
>
> The second one is a finished example, not a template. Nothing to fill in. You would attach your meeting notes and send it.
> `[NEEDS INPUT]` is not for you to type over. It tells ChatGPT to write that tag wherever your notes are missing a fact, so you can spot the gaps in its answer.

## Phrases worth memorizing

- **"Ask me up to 3 questions before you start."** The first draft comes out better.
- **"Don't make anything up. Mark gaps as [NEEDS INPUT]."** Cuts down on guessing. You still check.
- **"Critique this as a skeptical director, then improve it."**
- **"Give me 3 versions."** Pick one, or mix them.
- **"Shorter."** Works more often than you'd expect.
- **"Plain language. No filler."** Use this when a draft sounds like a machine wrote it.

## Where things go

| I want to… | Use |
|---|---|
| Ask a quick question or draft something | A regular ChatGPT chat |
| Work on the same program again and again | A **ChatGPT Project** with instructions and files |
| Pull from Jira or Confluence | The Jira and Confluence **connectors** (or attach an export) |
| Pull from SharePoint or Teams | Download the file and attach it |
| Process a folder of files, or run a weekly job from a saved template | **Codex** with the PM Workspace folder |

## Getting data out of our tools

There are two ways. Use a connector when there is one, and export when there isn't.

### Option 1: Connectors (Jira and Confluence)

We have ChatGPT connectors for **Jira** and **Confluence**. Once you've connected them, ChatGPT can look up tickets and pages for you, so there's nothing to export or attach. You only see what you already have access to.

- **Connect (one time):** ✏️ _[steps to come]_
- **Use it in a chat:** ✏️ _[steps to come]_
- **Example:** *"Using Jira, list everything in project EHR that's blocked, or past its due date and not Done, and tell me what to chase this week."*
- **Example:** *"Find our Confluence page on the go-live checklist and summarize it in 5 bullets."*

### Option 2: Export and attach (works for everything)

- **Jira:** run your search or filter → **Export → CSV** → attach to ChatGPT.
- **Confluence:** **•••** → **Export to Word** or **Export to PDF**, or copy and paste the page text.
- **SharePoint:** download the file and attach it.
- **Teams:** download the meeting transcript and attach it.

## Putting results back into our tools

Our Jira and Confluence are both Data Center, and they don't take the same formatting.

- **Confluence:** ask ChatGPT for the page "as Markdown in a code block" and copy it. In the Confluence editor, choose **Insert → Markup**, pick **Markdown**, and paste.
- **Jira:** Jira doesn't read Markdown. Ask ChatGPT to "format it in Jira wiki markup", then paste that into the ticket.
- **Email and Teams:** ask for plain text.
- **Connectors:** treat the Jira and Confluence connectors as look-up only for now. Publishing means pasting it in yourself.

## Do and don't

| Do | Don't |
|---|---|
| Use the company ChatGPT workspace only | Use a personal account for work |
| Check every name, date, and number | Send AI output without reading it |
| Give context ("this is for a VP") | Assume it knows our programs or acronyms |
| Revise in the same chat ("shorter, warmer") | Start over every time |
| Start a new chat for a new topic | Keep one giant chat for everything |
| Remove client-sensitive details if you're unsure | Paste patient data, passwords, or keys |

## Watch out for

- **Confident mistakes.** It can state a wrong date or name as if it were fact. Check against your source.
- **Filling gaps.** If your notes don't say who owns something, it may pick someone. Look for that.
- **What it can't know.** It doesn't know our programs, acronyms, or what happened in a meeting unless you give it the material.

## Remember

**You own the output.** ChatGPT writes the first draft. You edit it, and your name is on it.
