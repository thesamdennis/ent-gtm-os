---
name: opportunity-radar
description: Use when the seller asks where to focus selling time, to scan or prioritise enterprise accounts or a target list, to find net-new logos worth hunting, or to run the weekly Opportunity Radar (farmer or hunter mode).
---

# Opportunity Radar

Turn an account list into a ranked, evidence-backed answer to one question: **where should I spend my selling time this week, and why now?**

The output is a decision, not a news digest. Follow `shared/guardrails.md` and `shared/recommendation-contract.md` throughout.

## Step 0: Pick the mode

- **Farmer mode** (default): existing customers. Urgency comes from renewals, whitespace and live deals.
- **Hunter mode**: net-new logos with no installed base. Urgency comes only from a trigger, and the output is a door in.

Use hunter mode when the seller says "hunter", "net-new", "new logos", "targets" or "prospects", or when the list has no products owned. If a list mixes both, split it and run each mode on its half.

## Step 1: Get the list

**Farmer fields:** account, country, products owned, renewal date, contract value band, open opportunities, last senior (Director+) contact.

**Hunter fields:** account, country, industry, approximate employee count, ownership type (listed, government-linked, family-controlled, MNC subsidiary, private), known contacts or warm paths (optional).

If `context/accounts/*.yaml` files exist, read them first. If the list is missing, ask once with the field list. Blank fields are `unknown`; never fill them by guessing.

Scope: default to the top 10-15 farmer accounts by size or renewal proximity, or up to 30 hunter targets.

## Step 2 (hunter only): Fit gate

Run before any signal research, so no time is spent on accounts that were never going to buy. See `references/hunter-fit-gate.md`.

An account passes if it meets the size floor and at least two of: relevant industry, visible hiring or reskilling scale, a decision-maker reachable in-region. Failed accounts go to a short **Not a fit** list with one-line reasons. Do not research them further.

## Step 3: Signal scan (last 90 days)

Search each account separately. Never combine accounts in one query. Look for:
- Leadership change: CEO, CHRO, CFO, CTO, Head of TA or L&D
- Hiring surge or freeze; large open-role counts; new market, hub or site
- Layoffs, restructuring, cost programmes, shared-services moves
- M&A, mergers, divestments, multi-entity reorganisation
- Earnings, guidance changes, major contract wins
- AI or transformation announcements; reskilling programmes
- Workforce regulation (MOM, MAS, Malaysian HRD Corp, localisation rules)

Prefer APAC sources where relevant: SGX and Bursa announcements, The Business Times, The Straits Times, The Edge Malaysia, CNA, DealStreetAsia, Nikkei Asia, company newsrooms and annual reports.

Three filters on every hit:
- **Sourced:** link and date, or drop it.
- **Recent:** within 90 days, unless a structural change is still unfolding (flag it as older).
- **Material:** creates pressure one of the seller's products addresses.

If the seller supplies internal data (hiring volumes, known people moves, relationship notes), treat it as signal and mark it "internal".

"Nothing material found" is a valid result. Say it; do not pad.

## Step 4: Reasoning chain

Complete the chain for every material signal. Skip any signal you can't honestly complete.

**Farmer chain:** Signal → Pressure → Product (whitespace or expansion) → Buyer → Play → Next move

**Hunter chain:** Trigger → Pain → Entry buyer → Angle → Door in → First meeting
- **Entry buyer:** the title most likely to feel the pain and take a first meeting. Often not the final economic buyer.
- **Angle:** a one-line point of view on their pain, specific to this trigger. Not a product pitch.
- **Door in:** the warmest route available, ranked: (1) existing relationship or ex-colleague, (2) mutual connection or shared board member, (3) partner or SI, (4) peer customer reference, (5) event or community, (6) cold outreach. Name which applies; use titles, not invented names.

Plays and angles come from `references/play-library.md`.

## Step 5: Tier

Tiers, not numeric scores. One line of reasoning per account.

**Farmer**
- **Act now** (cap 5): strong recent signal with a clear play, OR renewal within 180 days with a value or relationship gap, OR a live deal at risk.
- **Watch:** weaker or early signal, or a play without a timing trigger. Re-check in 30 days.
- **Park:** nothing material. Revisit next quarter.

**Hunter**
- **Pursue now** (cap 10): passed the fit gate, has a trigger in the last 90 days, and a door in at level 1-4.
- **Warm up:** fit plus trigger, but only a cold door. This week's job is building access (events, mutual connections, content to the right people), not cold outreach that burns the logo.
- **Not yet:** fit but no trigger. Park until something changes.

If more qualify for the top tier than the cap allows, rank by deal size times urgency and push the rest down.

## Step 6: Output

Lead with the answer.

**Farmer**

**This week, focus on:** Act now accounts in order, one line each.

One card per Act now account:
> **[Account]: Act now** (Confidence: High / Medium / Low)
> - **What changed:** signal(s), each with source and date
> - **Why it matters:** the pressure
> - **Whitespace or expansion:** product
> - **Likely buyers:** titles
> - **Play:**
> - **Next move (this week):**
> - **Don't:** (if relevant)
> - **Needs your call:**

**Hunter**

**This week, pursue:** Pursue now accounts in order, one line each.

One card per Pursue now account:
> **[Account]: Pursue now** (Confidence: High / Medium / Low)
> - **Trigger:** with source and date
> - **Pain:**
> - **Entry buyer:** title
> - **Angle:** one line
> - **Door in:** route and level (1-6)
> - **Opening line:** one or two sentences that lead with the trigger and the angle. No hedging openers.
> - **First meeting ask:** what the meeting is for, in the buyer's terms
> - **Don't:** (if relevant)
> - **Needs your call:**

Then a compact **Watch** or **Warm up** table (account, signal, what would promote it) and a **Park** or **Not yet** list (names only). Hunter mode also lists **Not a fit** accounts with reasons.

Close with:
- **Time split:** farmer default ~60% Act now, 25% Watch and live deals, 15% other. Hunter default ~50% Pursue now outreach and meetings, 30% Warm up access-building, 20% research and list-building.
- **The one meeting to book** this week.

## Step 7: Write back (optional)

If account YAML files are in use, update each account's `radar` section: tier, signals (with links), play, next move, run date. Touch nothing else.

## Learning loop

When the seller reports an outcome (meeting booked, reply, deal won or lost, a play that fell flat), suggest a specific edit to `references/play-library.md`, or to the fit gate if a "fit" account turned out wrong.
