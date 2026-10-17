---
name: consensus-builder
description: Use when the seller wants to map a buying committee, find missing or blocking stakeholders, check champion strength, prepare for a key meeting, or build stakeholder-specific business cases and value packs the champion can forward internally.
---

# Consensus Builder

Help the seller win the meeting they're not in. Large deals rarely die on the demo. They die because finance doesn't see the return, IT sees risk, procurement arrives late, the economic buyer never engages, or the champion can't sell internally.

Follow `shared/guardrails.md` and `shared/recommendation-contract.md`.

## Step 1: Gather the deal context

Ask for (or read from `context/accounts/<account>.yaml` → `stakeholders`, `deals`, `notes`):
- The deal: what's being bought, value band, target close date, stage
- Everyone involved so far: title, what they've said or done, last contact
- Meeting notes, email threads or call summaries the seller can paste
- How the customer says they'll decide, if known

Use titles unless the seller provides names. Quote stakeholders only from what the seller supplied.

## Step 2: Build the decision graph

One row per stakeholder. See `references/stakeholder-roles.md` for role definitions.

| Stakeholder | Role | Influence | Stance | What they care about (their words) | Evidence | Last touch | Next move |
|---|---|---|---|---|---|---|---|

- **Role:** economic buyer, champion, coach, technical evaluator, user lead, finance approver, procurement, legal or security, blocker, unknown.
- **Influence:** High / Medium / Low.
- **Stance:** Supporter / Neutral / Sceptic / Opponent / Unknown. Unknown is common; say so.
- **What they care about:** from their own words where possible. Mark inferences "(inferred)".

## Step 3: Interrogate the graph

Answer each question explicitly, with evidence:

1. **Who's missing?** Compare against the role template. Flag any absent role that normally decides or blocks deals this size (finance, procurement, IT and security are the usual gaps).
2. **Is there an economic buyer, and have we met them?** If not, this is the top risk.
3. **Single-threaded?** If one champion holds the deal, say so plainly.
4. **Champion test:** do they have power, access to the economic buyer, and a personal win? Missing any one makes them a coach, not a champion.
5. **Where do goals conflict?** For example, HR wants speed, finance wants cost cut, IT wants fewer vendors. Name the conflict and who arbitrates it.
6. **Who could quietly kill it?** The sceptic with veto power, or the process owner nobody has met.
7. **What does the champion need to sell this internally?**

## Step 4: Value packs

For each stakeholder who must say yes, draft a short forwardable piece in their language. Templates in `references/value-pack-templates.md`.

| Audience | Leads with |
|---|---|
| CEO or BU head | Strategic outcome and risk of inaction |
| CFO or finance | Baseline cost, conservative and expected scenarios, payback |
| CHRO or HR | Talent outcomes: speed, quality, retention, capability |
| IT or security | Integration, data handling, implementation effort |
| Procurement | Commercial structure, decision timeline, comparison basis |

**Business case rules:**
- Use the customer's own numbers where supplied. Mark every assumption.
- Show three scenarios: baseline (do nothing), conservative, expected. Never lead with the best case.
- Payback in months, from the conservative scenario.
- Include a plain **value sheet** (problem, current cost, proposed change, measurable outcome, assumptions) structured so a buyer's AI comparing vendors can parse it as easily as a human.

## Step 5: Output

> **Deal:** [account, what, value band, target close]
> **Consensus status:** Strong / Building / At risk — one line why
>
> **Decision graph** (table)
>
> **Gaps and risks** (ranked, each in recommendation-contract form)
>
> **Next three moves** (who, what, by when; at least one must close the biggest gap)
>
> **Value packs** (drafts, clearly marked "draft for seller review")
>
> **Needs your call:** politics, history and relationships the skill can't see

## APAC lens

- Formal hierarchy often means the decider doesn't attend working meetings. Ask who the attendees report to.
- In government-linked and family-controlled groups, identify the group-level or family approver early.
- Disagreement may not be voiced in group settings. A quiet stakeholder is "Unknown", not "Supporter".

## Write back (optional)

Update the account YAML `stakeholders` section with the decision graph. Touch nothing else.
