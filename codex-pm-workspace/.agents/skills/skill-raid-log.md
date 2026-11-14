---
name: raid-log
description: Build or update a RAID log (Risks, Assumptions, Issues, Dependencies) or run a pre-mortem from program files. Use when the user asks for a risk list, RAID log, risk register, dependency list, pre-mortem, or "what could go wrong".
---

# RAID log

## What the letters mean

- **Risk**: something that *might* happen and would hurt the program.
- **Assumption**: something we're treating as true but haven't confirmed.
- **Issue**: a problem that is *already* happening.
- **Dependency**: something we're waiting on from another team, vendor, or the client.

## Steps

1. **Look for an earlier RAID log first.** Check `outputs/` (and `inbox/`) for the most recent file with `raid-log` in its name. If you find one, update it instead of starting over:
   - Keep every existing ID. Never renumber, and never reuse an ID.
   - Don't delete rows. If an item is resolved, set its Status to "Closed" and add the date and how it was resolved.
   - Update the rows that changed and put today's date in "Last updated".
   - Give new items the next free ID for their type and mark them 🆕.
   - Save the result as a new dated file. Leave the old one as it is.
2. Read the files the user points to in `inbox/`. If they don't say which, read all of them.
3. Find every risk, assumption, issue, and dependency. Look especially for:
   - Dates that depend on another team or the client.
   - Security, compliance, or authorization steps (e.g. FedRAMP or state approvals).
   - Single points of failure: one person who knows everything, one environment, one vendor.
   - Things people said they "assume" or "should be fine".
4. Give each item an ID by type: R1, R2… for risks, A1… for assumptions, I1… for issues, D1… for dependencies.
5. Rate each risk: **Likelihood** (High/Med/Low) and **Impact** (High/Med/Low).
6. Fill in the table below. Sort open items by most severe first, with closed items at the bottom.
7. Save to `outputs/YYYY-MM-DD-raid-log.md`.

## Template

```
# RAID log: [program], [date]

| ID | Type | Description | Likelihood | Impact | Owner | Response / next step | Due | Status | Last updated |
|---|---|---|---|---|---|---|---|---|---|
| R1 | Risk | ... | High | High | [NEEDS INPUT] | ... | ... | Open | [date] |

## Top 3 to raise with leadership
1. ...
```

## Pre-mortem mode

If the user asks for a pre-mortem: imagine it's 6 months from now and the program failed.
List the 10 most likely reasons it failed, then turn each one into a row in the RAID log.

## Rules

- Write each item so someone outside the team can understand it.
- Every risk needs a response: avoid, reduce, transfer, or accept.
- Don't invent owners. Use `[NEEDS INPUT: owner]`.
