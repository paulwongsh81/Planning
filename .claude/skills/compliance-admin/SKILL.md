---
name: compliance-admin
description: Tracks CPD hours, licence renewal dates, FNA/KYC document completeness, and filing deadlines for Paul's advisory practice, and flags what needs attention. Use when Paul asks about compliance status, CPD hours, licence renewal, KYC/FNA completeness, filing deadlines, or asks to run a compliance check.
---

# Compliance & Admin

Purpose: catch compliance and admin items before they become deadlines,
not after. This domain never files or submits anything — it tracks,
checks, and flags. See the parent CLAUDE.md for the guardrails this
domain operates under.

## What it watches

- **CPD hours** — running total for the current cycle vs. the
  requirement, and time left to close any gap.
- **Licence renewal date(s)** — flag once inside 90 days of expiry,
  escalate urgency inside 30.
- **FNA/KYC document completeness** per client file — missing
  signatures, stale fact-finds, expired ID.
- **Filing/submission deadlines** — anything with a hard date
  (regulatory returns, internal audits, etc).

## Where the data lives

On first run, ask Paul where each of these is currently tracked (a
spreadsheet, IPP's internal system, a Drive doc, email confirmations)
rather than assuming a system. If nothing exists yet for one of them,
offer to set up a simple tracker — e.g. a sheet in this repo or in
Drive — rather than inventing numbers. Never fabricate a CPD total,
deadline, or document status that hasn't actually been pulled from a
real source.

## What a check looks like

1. Pull current state from wherever it's tracked.
2. Compare against requirements/deadlines.
3. Produce a short status list: on track / needs attention soon /
   overdue.
4. For anything "needs attention" or worse, say what the specific
   action is and by when — don't just flag, propose the fix.

## Autonomy

Ongoing — this domain can run its checks on a recurring schedule
(weekly is a reasonable default) without asking first each time. It
never:

- submits, files, or renews anything itself
- contacts a client, IPP, or a regulator on Paul's behalf

It only tracks and flags. Paul acts on what it surfaces.

## Output

A short status note, not a report — readable in under a minute. Lead
with anything overdue or urgent; routine "on track" items get one line
each.
