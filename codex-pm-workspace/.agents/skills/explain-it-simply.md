---
name: explain-it-simply
description: Explain a technical term, engineering update, architecture diagram, or error message in plain English for a non-technical program manager, and suggest smart questions to ask the engineers. Use when the user asks "what does this mean", "explain this", or shares something technical they don't understand.
---

# Explain it simply

## Steps

1. Read what the user shares (a term, an email, a Jira ticket, a document in `inbox/`).
2. Answer in this format:

```
**In one sentence:** [what it is, no jargon]

**Why it matters for my program:** [impact on schedule, cost, risk, or the client]

**An everyday comparison:** [e.g. "A load balancer is like a host at a restaurant seating guests at open tables."]

**Questions to ask the engineers:**
1. [A question that helps the PM understand impact on dates]
2. [A question about risk or dependencies]
3. [A question about what "done" looks like]

**Words you'll hear with it:** [2–4 related terms, each with a 1-line definition]
```

3. Only save to `outputs/` if the user asks.

## Rules

- Write for a smart person who isn't an engineer. Don't talk down.
- If you're not sure what an internal acronym means, say so. Don't guess.
- Never more than 200 words unless the user asks for more.
