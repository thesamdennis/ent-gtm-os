# Evals: backtesting the skills

Before trusting a skill live, test it against deals whose outcomes you already know.

## How

1. Pick 10 closed deals: a mix of wins, losses, and renewals that slipped or expanded.
2. For each, write a case file (`evals/cases/<id>.yaml`, local only) describing the account **as it looked at the time**, before the outcome. Anonymise names.
3. Run the relevant skill on the case without revealing the outcome.
4. Score with the rubric below and record results in `evals/results.md`.

## Rubric

| Skill | Question | Score |
|---|---|---|
| Opportunity Radar | Did it tier the account correctly (would it have told you to act)? | 0 / 1 |
| Opportunity Radar | Was the play the one that actually worked (or would have)? | 0 / 1 / 2 |
| Consensus Builder | Did it flag the stakeholder gap that mattered? | 0 / 1 |
| Deal Control Tower | Did it raise the risk before the slip, and was the "don't" right? | 0 / 1 / 2 |
| All | Any fabricated fact? (any yes = fail the case) | pass / fail |

## Case template

See [`case-template.yaml`](case-template.yaml). Real cases stay local; `.gitignore` excludes `evals/cases/`.
