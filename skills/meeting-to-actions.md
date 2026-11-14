---
name: meeting-to-actions
description: Turn meeting notes or a transcript into decisions, action items with owners and due dates, open questions, and a ready-to-send follow-up email. Use when the user shares meeting notes or a transcript, or asks for action items, a recap, or a follow-up email.
---

# Meeting → actions

## Steps

1. Read the meeting notes or transcript the user names in `inbox/`.
2. Pull out four things:
   - **Decisions**: things the group agreed on.
   - **Action items**: who will do what, by when.
   - **Open questions**: things raised but not answered.
   - **Risks**: anything that could delay or derail the program.
3. Only list an owner or due date if someone actually said it. Otherwise write `[NEEDS INPUT: owner]` or `[NEEDS INPUT: due date]`.
4. Draft a short follow-up email the user can send to attendees.
5. Save everything to `outputs/YYYY-MM-DD-meeting-recap-[topic].md`, using today's date in the file name. The meeting date goes inside the file.

The file has two parts with different formatting:
- **The recap** is Markdown (headings and tables), for Confluence or your own records.
- **The email** is plain text with no formatting marks at all (no `#`, no `*`, no tables), so it can be pasted straight into Outlook. Put it inside a code block so it copies cleanly.

## Template

````
# Meeting recap: [meeting name], [meeting date]

## Decisions
1. ...

## Action items
| # | Action | Owner | Due | Jira? |
|---|---|---|---|---|
[In the "Jira?" column, write "Yes" if this should become a Jira ticket.]

## Open questions
- ...

## Risks raised
- ...

---

## Follow-up email (plain text, ready to paste)

```
Subject: [Meeting name]: recap and next steps

Hi all,

Thanks for your time on [meeting date]. Here's what we agreed and who owns what.

DECISIONS
- ...

ACTION ITEMS
- [Owner]: [action], by [date]

OPEN QUESTIONS (please reply if you own one of these)
- ...

Let me know if I missed anything.

[Name]
```
````

## Rules

- Keep the email under 200 words.
- Use the meeting's actual date in the email, not "today". The recap is often written days later.
- Quote a person only if the exact words matter, and only if they're in the notes.
