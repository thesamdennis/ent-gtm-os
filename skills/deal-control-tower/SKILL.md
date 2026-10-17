---
name: deal-control-tower
description: Use when the seller wants a deal review, asks what could kill a deal or renewal, wants to know which live deals are slipping, or wants a renewal-risk check from 180 days before renewal.
---

# Deal Control Tower

Catch a large deal sliding before it's lost, and say specifically why and what to do. A generic "deal health 61/100" gets ignored. "The economic buyer hasn't been in a meeting for 31 days and procurement arrived without a timeline" gets acted on.

Follow `shared/guardrails.md` and `shared/recommendation-contract.md`.

## Step 0: Pick the mode

- **Deal mode** (default): open new-business or expansion opportunities.
- **Renewal mode:** contracts renewing within 180 days. Use when the seller says renewal, or when a renewal date is within 180 days.

## Step 1: Gather the deal state

Per deal, ask for or read from `context/accounts/<account>.yaml` → `deals`, `stakeholders`, `notes`:
- Stage, value band, close date, and any changes to either since last review
- Last meeting date and who attended; next meeting booked (yes or no)
- Stakeholder coverage (or the Consensus Builder graph, if it exists)
- Mutual action plan or agreed next steps, and which are overdue
- Pricing, procurement, legal and security status
- Competitor mentions, objections, open questions
- Renewal mode also: usage or adoption trend, support issues, sponsor changes, value delivered vs promised

If the seller ran this before, compare against the previous state. **Change is the signal.**

## Step 2: Check risk signals

See `references/risk-signals.md` for the full catalogue. Core checks:

| Area | Risk if |
|---|---|
| Executive engagement | Economic buyer absent 30+ days, or never met |
| Momentum | No next meeting booked; mutual plan steps overdue |
| Timeline | Close date moved; stage unchanged longer than usual |
| Coverage | Single-threaded; champion quiet or changed roles |
| Value | Pricing discussed before value was confirmed by the buyer |
| Process | Procurement, legal or security engaged with no agreed decision timeline |
| Competition | New competitor mentioned; buyer asking comparison questions |
| Renewal | Usage down; sponsor left; open escalations; value story not refreshed |

## Step 3: Status

- **Green:** on track, no material new risk.
- **Amber:** one or two material risks; recoverable with action this week.
- **Red:** the deal is likely to slip or be lost without a change of approach.

Report the **change** (e.g. Green → Amber) and the specific reasons. Never a bare status.

## Step 4: Output

Lead with the deals that changed. Unchanged greens go in one line at the end.

> **[Account — deal]: Green → Amber** (Confidence: High / Medium / Low)
>
> **What changed:** two to four specific facts, each with its evidence (date, note, email)
> **Biggest risk:** one sentence (e.g. "This is turning into a pricing exercise")
> **Strategy:** what to re-anchor on
> **Do this week:** one to three actions, owner and date
> **Don't:** the tempting move that makes it worse (e.g. "Don't send another revised proposal yet")
> **Suggested next meeting:** who, and the purpose in their terms
> **Needs your call:**

**Renewal mode** adds:
> **Renewal clock:** T-minus days
> **Value delivered vs promised:** what the evidence shows
> **Expansion signal:** if any (only if no open escalation)
> **Save or grow:** which play, and why

Close with **Portfolio view:** a short table of every deal (account, stage, status, change, next action), sorted by risk then size.

## Guardrails specific to this skill

- Never draft or send pricing, discounts or concessions; recommend only.
- Don't propose expansion to an account with an open escalation or red status. Fix the relationship first.
- If the seller's data is thin, say which three facts would most change the assessment.

## Write back (optional)

Update `deals` in the account YAML: status, change, risks, next actions, review date. Touch nothing else.
