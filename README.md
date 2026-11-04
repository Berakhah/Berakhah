## Bereket Tilahun

Backend and security engineer in Addis Ababa, open to remote work. I build Python services that fail closed, show their evidence, and say plainly what they don't do yet.

**Focus:** MCP and agent security · LLM evaluation · document automation for finance · Python, FastAPI, Postgres, Docker

### Projects

| Project | What it does | Proof |
| --- | --- | --- |
| [agent-perimeter](https://github.com/Berakhah/agent-perimeter) | Security scanner for MCP servers and tool-using agents: passive checks, scope-gated active probes, drift detection, SARIF and a GitHub Action | 750+ tests, `mypy --strict`, clean-machine CI, tagged releases |
| [ledger-sense](https://github.com/Berakhah/ledger-sense) | Reads construction pay applications, checks the arithmetic, routes doubtful fields to human review, writes unpaid Bills to QuickBooks | 1,129 tests, Decimal-only money, idempotent writeback, hash-chained audit log |
| [ground-truth](https://github.com/Berakhah/ground-truth) | Evaluation harness for LLM field extraction with a seeded golden corpus, judge agreement and bootstrap confidence intervals | 90% test coverage; real model results not yet published |
| [aztdp](https://github.com/Berakhah/Adaptive-Zero-Trust-Defense-Platform--AZTDP-) | Gateway that scores each request's risk and lets OPA decide allow, step-up, revoke or deny, across a 16-service Compose stack | 227 tests, signed releases with SBOMs |
| [selector-drift](https://github.com/Berakhah/selector-drift) | Self-healing extraction for portals with no API; nothing healed is written until it passes four validation gates | 1,900+ tests; install still needs a private dependency |

### How I work

- I build with AI pair-programming. The design decisions, reviews and the tests that prove them are mine.
- Every headline number links to the script that regenerates it, with its sample size.
- Each README lists what is unfinished.

### Contact

[Portfolio](https://berakhah.github.io) · [LinkedIn](https://www.linkedin.com/in/bereket-tilahun-488003232) · [email redacted]
