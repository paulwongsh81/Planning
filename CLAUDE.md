# Paul's Operating Model

This repo is the operating system for Paul Wong's advisory practice
(Financial Adviser, IPP) and daily life — a right-sized version of a
"leads delegate to domains, domains delegate to tasks" agent setup.
Full rationale and diagram:
https://claude.ai/code/artifact/9684e0bf-52ad-4a15-ae2b-1cc0bbc85889

## Structure

Two leads own everything:

- **Practice Lead** — the business: client reviews, compliance, content,
  prospecting, market research.
- **Life Lead** — everything else: daily planning, personal admin.

Each lead delegates to **domains** (a persistent session or a subagent,
depending on how much standing memory the work needs), and domains spin
up **task agents** for single pieces of work, then let them disappear.

## Domains

| Domain | Reports to | Status | Playbook |
|---|---|---|---|
| Compliance & Admin | Practice Lead | **Active** | `.claude/skills/compliance-admin/SKILL.md` |
| Client Reviews & Portfolio Prep | Practice Lead | Planned | — |
| Content & Newsletter | Practice Lead | Active (existing skill) | `paul-newsletter` |
| Prospecting & Touchpoints | Practice Lead | Planned | — |
| Market & Product Research | Practice Lead | Planned | — |
| Daily Planning & Admin | Life Lead | Active (existing skill) | `morning` |

To add a domain: write its playbook as a skill first, run it manually a
few times, then automate the recurring part with a Routine. Don't build
a domain that isn't causing pain yet — one working domain beats six
half-built ones.

## Guardrails

These apply to every domain, always:

1. **Nothing client-facing sends unread.** Advice, recommendations,
   emails, filings — Paul reads it before it leaves. No autonomous send
   on regulated output.
2. **Confirm what data is allowed where.** Check with IPP compliance
   before putting real client details into a session, if that isn't
   already settled.
3. **Keep the paper trail.** Commits in this repo (or an explicit log)
   record what was AI-drafted, what was human-approved, and when.
4. **Match autonomy to risk.** Research and drafting can run unattended
   for days. Anything touching a specific client's money or advice gets
   a same-day checkpoint.

## Cadence

Paul checks in with the two leads roughly twice a day — a short morning
pass and a short evening approval pass. Leads handle their domains in
between and escalate only what needs a judgment call. Most days:
10-20 exchanges total, almost all of it with a lead, not a domain or
task agent directly.
