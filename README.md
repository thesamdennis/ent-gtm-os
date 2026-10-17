# ENT GTM OS

An operating system for enterprise sellers, built as three Claude skills that share one account context layer.

> Find the opportunity → Win the room you're not in → Protect the deal to signature and renewal.

Most AI sales tooling automates tasks (emails, summaries, CRM updates). This repo does something different: it improves **decision quality**, meaning where a seller spends time, who they need to win, and what could kill the deal.

## The three skills

| Skill | Question it answers | Main output | Cadence |
|---|---|---|---|
| [`opportunity-radar`](skills/opportunity-radar/SKILL.md) | Where should I spend my selling time, and why now? | Tiered accounts with cited signals, play and next move. **Farmer** and **hunter** modes. | Weekly, plus on signal |
| [`consensus-builder`](skills/consensus-builder/SKILL.md) | Who do I need to win, and what does each person need? | Decision graph, coverage gaps, conflicts, stakeholder value packs | Before and after key meetings |
| [`deal-control-tower`](skills/deal-control-tower/SKILL.md) | What could kill this deal, including at renewal? | Specific risk changes with do and don't actions | Weekly on live deals; T-180 renewal mode |

Each skill runs on its own. Together they read from and write back to the same account files in `context/`.

## Design principles

1. **Context first, agents second.** Every skill reads `context/accounts/<account>.yaml`. Better context beats more agents.
2. **One recommendation contract.** Every recommendation states what changed, why it matters, evidence, confidence, action, expected outcome and whether seller approval is needed. See [`shared/recommendation-contract.md`](shared/recommendation-contract.md).
3. **Tiers, not fake-precise scores.** Act now / Watch / Park beats "87/100".
4. **No source, no signal.** Nothing is invented. Unknown stays unknown.
5. **Human in the loop.** Skills draft and recommend. Nothing is sent, priced or discounted without the seller.
6. **APAC-native.** SGX, Bursa and local press as first-class sources; hierarchy, government-linked and family-business dynamics flagged explicitly.

## Repo layout

```text
ent-gtm-os/
├── .claude-plugin/plugin.json      # installs all three skills as one plugin
├── skills/
│   ├── opportunity-radar/          # SKILL.md + play library + hunter fit gate
│   ├── consensus-builder/          # SKILL.md + stakeholder roles + value pack templates
│   └── deal-control-tower/         # SKILL.md + risk signal catalogue
├── shared/                         # recommendation contract, account schema, guardrails
├── context/accounts/               # one YAML per account (synthetic examples only in git)
├── evals/                          # backtest cases: did the skill call it right?
└── docs/                           # architecture and roadmap
```

## Getting started

**In Claude (chat or Claude Code):**
1. Install the plugin from this repo, or copy any `skills/<name>/` folder into your skills directory.
2. Copy `context/accounts/_template.yaml` for each account you want covered (keep real ones local, see below).
3. Ask: "Run my Opportunity Radar" (farmer) or "Run the Radar in hunter mode on these targets".

**Try it with the synthetic accounts first:** `context/accounts/example-*.yaml`.

## Data rule (read this)

This repo is a framework. **Real customer, contract or CRM data never goes in git.** `context/accounts/` ignores everything except `_template.yaml` and `example-*.yaml`. Run real account data only inside tools your employer has approved.

## Roadmap

See [`docs/roadmap.md`](docs/roadmap.md). Short version: Radar → backtest → Consensus Builder → Control Tower → connectors (email, calendar, CRM) → event triggers.

## Author

Sam Dennis — enterprise seller, ASEAN. Built with Claude.
