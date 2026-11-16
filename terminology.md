# Terminology: the words you'll run into

New to AI tools? Start here. Each term gets a plain explanation, and where it helps, an example from our own work.
You don't need to learn these up front. Come back when a word in the kit stops you.

---

## The basics

**AI model.** The engine behind ChatGPT. It has read a huge amount of text and predicts what a good answer looks like. It doesn't look things up in a database unless it's connected to one, and it doesn't know anything about our programs unless you tell it.

**ChatGPT.** OpenAI's AI assistant. We use the company version, which is set up for work data. Always sign in with your company account, never a personal one.

**Prompt.** Whatever you type to the AI. A question, a request, a pasted document with instructions on top. The better the prompt, the better the answer.

**Response** (or **output**). What the AI writes back.

**Chat.** One conversation with ChatGPT. Everything you've said in a chat shapes the next answer in that chat. A new chat starts fresh.

**Context.** The background the AI needs to do the job well. Who the audience is, what the program is, what happened last week. If a new teammate would need to know it, so does ChatGPT.

**Hallucination.** When the AI states something false with full confidence. A wrong date. A person who wasn't in the meeting. A ticket number that doesn't exist. It's the main reason you check every name, date, and number before you send anything.

**First draft.** The right way to think about anything the AI writes. You edit it. Your name goes on it.

**Context window.** How much text the AI can keep in mind at once. In a very long chat, it can lose track of details from early on. If answers start ignoring things you said earlier, start a new chat and paste in what matters.

**Token.** A chunk of text, roughly three quarters of a word. You'll see it in error messages about length limits. You don't need to count them.

---

## ChatGPT features

**Company workspace.** Our organization's ChatGPT account. It's where your work chats belong, and it's where admins control which features and connectors are turned on.

**Attach** (or **upload**). Adding a file to a chat with the paperclip or plus button. A Jira CSV, a meeting transcript, a Word document. ChatGPT reads it and works from it.

**ChatGPT Project.** A folder inside ChatGPT for one program. It holds your chats, files you use often, and a set of standing instructions. Every chat you start inside the Project follows those instructions without you repeating them.

**Project instructions.** The standing rules for a Project. Ours are in `04-chatgpt-project-instructions.md`. You fill in two lines about yourself and leave the rest.

**Custom instructions.** Like Project instructions, but they apply to all your chats. Found under Settings → Personalization. The box is small, so only the short parts of our instructions fit there.

**Memory.** A ChatGPT feature that can carry some details from one chat to the next, if it's turned on. Useful, but don't depend on it for work. Put anything important in your Project or your prompt.

**Connector** (ChatGPT also calls these **apps**). A link between ChatGPT and another tool. We have them for Jira and Confluence. With a connector, you can ask ChatGPT about tickets or pages without exporting anything. It only sees what you already have permission to see.

**Custom GPT.** A saved assistant with its own instructions and files that you can share with your team from one link. Only available if our workspace allows it.

**ChatGPT desktop app.** ChatGPT as a program on your computer instead of a browser tab. It can open a folder on your computer and work with the files in it. It has a selector above the message box for switching between plain ChatGPT and Codex.

---

## Codex and the PM Workspace

**Codex.** OpenAI's AI that works directly with files on your computer. You point it at a folder, ask in plain English, and it reads files and saves new ones. It's built into the ChatGPT desktop app. There's also a version you run in a terminal.

**Terminal** (or **command line**). A text window where you type commands instead of clicking. Terminal on a Mac, PowerShell on Windows. Only the `06-demo-codex-cli.md` demo uses it. You can skip it entirely.

**Codex CLI.** The terminal version of Codex. "CLI" stands for command-line interface.

**PM Workspace.** The `codex-pm-workspace` folder in this kit. Your files go in `inbox/`. Codex puts what it makes in `outputs/`.

**AGENTS.md.** A plain-English instruction file that sits in the PM Workspace. Codex reads it every time it starts in that folder. It's the Codex version of Project instructions. You edit the lines marked ✏️.

**Skill.** A saved recipe for a job you do often, like a status report or a RAID log. It tells the AI the steps and the layout to follow, so the output is consistent from week to week. The kit has five. Each one is a file called `SKILL.md` inside its own folder.

**Calling a skill.** Usually you don't have to. Ask for "a status report" and Codex picks the matching skill on its own. To pick one yourself, type `$` and the skill's name, like `$raid-log`.

**Session.** One run of Codex, from when you start it until you close it or start fresh. Similar to a chat in ChatGPT.

**Permission prompt** (or **approval**). Codex stopping to ask before it does something. Reading files in the folder and saving to `outputs/` are normal, so approve those. If it wants to install software, use the internet, or touch files outside the folder, say no.

**Hidden folder.** A folder whose name starts with a dot, like `.agents`. Your computer hides these by default. The skills live in one. You don't need to open it. It just has to be there.

---

## Prompting terms

**Placeholder.** A blank in a prompt template. In our prompt library, anything in capitals inside brackets, like `[MEETING NAME]`, is yours to replace.

**`[NEEDS INPUT]`.** Not a blank. It's an instruction telling the AI to write that tag wherever your source is missing a fact, instead of guessing. You fill those gaps in afterward.

**Lower-case brackets.** Things like `[who]` or `[what]` in the Jira story format. These are for the AI to fill in. Leave them alone.

**Role prompt.** Asking the AI to take on a point of view. "Act as a skeptical program director." "Act as the client's IT director, who is frustrated about delays." Good for practice and for stress-testing a plan.

**Iterate** (or **revise**). Improving an answer by telling the AI what to change. "Shorter." "Warmer." "Use the dates from my notes." Faster than starting over, almost every time.

**Template.** A fixed layout the AI fills in. Our status report has one, so every report has the same sections in the same order.

---

## Files and formats

**Plain text.** Text with no formatting at all. Files ending in `.txt`. The safest format for pasting into email or Teams, and the easiest for Codex to read.

**Markdown.** Plain text with a few simple marks for formatting. `#` makes a heading, `**word**` makes bold, a dash starts a bullet. ChatGPT writes in Markdown by default. Files end in `.md`. Confluence can take it through Insert → Markup → Markdown.

**Jira wiki markup.** Jira's own formatting marks, which are different from Markdown. `h3.` makes a heading, `*word*` makes bold. Our Jira doesn't read Markdown, so ask the AI to "format it in Jira wiki markup" when the text is going into a ticket.

**Code block.** A gray box in a ChatGPT answer with a copy button. Ask for something "in a code block" when you want to copy it exactly, with nothing changed by the chat window.

**CSV.** A spreadsheet saved as plain text, with commas between the columns. What you get when you export from Jira. Both ChatGPT and Codex read CSV files well.

**`.vtt` file.** A Teams meeting transcript saved as plain text. Pick this format when Teams offers it.

---

## Jira terms used in this kit

**Data Center.** The version of Jira and Confluence we run, hosted by us rather than by Atlassian. It matters because some menus and formatting rules differ from the cloud version you'll see in online guides.

**JQL.** Jira Query Language. The search language behind Jira's advanced search. You don't need to learn it. Describe what you want and ask ChatGPT to write the query.

**Export.** Downloading a list of Jira tickets as a file, usually CSV. From a search or filter, choose Export.

**Bulk import.** Creating many Jira tickets at once from a CSV file. The AI can draft the CSV. Check it with the Jira admin before importing, because field names and linking rules depend on how our Jira is set up.

**Epic Link and Parent Link.** Two different Jira fields for connecting tickets. Epic Link ties a Story or Task to its Epic. Parent Link ties an Epic to its Initiative, if our Jira has that field.

---

## Safety terms

**Sensitive data.** Anything that shouldn't go into an AI tool without checking the policy first. Patient information, passwords, access keys, and client details you'd be uncomfortable seeing outside the team. When in doubt, leave it out or swap in a stand-in like "Client A".

**AI-use policy.** The company's rules for what you can put into ChatGPT and how you can use what comes out. It overrides anything in this kit.
