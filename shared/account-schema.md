# Account context schema

One YAML file per account in `context/accounts/`. All three skills read it; each writes back only its own section.

| Section | Owned by | Contents |
|---|---|---|
| `account` | Seller | Name, country, industry, size, ownership type, decision HQ |
| `relationship` | Seller | Motion (farmer or hunter), products owned, contract value band, renewal date |
| `radar` | Opportunity Radar | Latest tier, signals, play, next move, last run date |
| `stakeholders` | Consensus Builder | Decision graph rows |
| `deals` | Deal Control Tower | Live opportunities, status, risk changes |
| `notes` | Seller | Free text: history, politics, what's worked |

Rules:
- `unknown` is a valid value. Never fill a blank by guessing.
- Dates as `YYYY-MM-DD`.
- Contract values as bands (`<50k`, `50-150k`, `150-500k`, `500k+`), not exact figures, so files are safer to share.
- Ownership type matters in APAC: `listed`, `government-linked`, `family-controlled`, `MNC-subsidiary`, `private`.

See [`../context/accounts/_template.yaml`](../context/accounts/_template.yaml) for the full template.
