## Bereket Tilahun

I test whether one customer can reach another customer's data in Supabase, Next.js and Stripe apps, and prove every finding with a script you can re-run.

Backend and security engineer in Addis Ababa, open to remote work. I build Python services that fail closed, show their evidence, and say plainly what they don't do yet.

**Focus:** Supabase / Postgres RLS security audits for AI-built apps · MCP and agent security · Python, FastAPI, Next.js, Postgres

**Available for pre-launch security audits** of apps built with Lovable, Bolt, Cursor or Next.js + Supabase. See the sample audit below, then [hire me on Upwork](https://www.upwork.com/freelancers/~01645da719eb4829ed).

### Projects

| Project | What it does | Proof |
| --- | --- | --- |
| [shopfast-demo](https://github.com/Berakhah/shopfast-demo) | Sample security audit: a demo Supabase + Stripe store with eight flaws AI coding tools commonly ship, planted on purpose and marked in the code | 8 findings (3 Critical, 2 High, 3 Medium), all 8 proven in a live run; 6 re-proven by `npm run poc` |
| [agent-perimeter](https://github.com/Berakhah/agent-perimeter) | Security scanner for MCP servers and tool-using agents: passive checks, scope-gated active probes, drift detection, SARIF and a GitHub Action | 940 Python test functions, `mypy --strict`, clean-machine CI, tagged releases |
| [ledger-sense](https://github.com/Berakhah/ledger-sense) | Reads construction pay applications, checks the arithmetic, routes doubtful fields to human review, writes unpaid Bills to QuickBooks | 921 Python test functions, Decimal-only money, idempotent writeback, hash-chained audit log |
| [ground-truth](https://github.com/Berakhah/ground-truth) | Evaluation harness for LLM field extraction with a seeded golden corpus, judge agreement and bootstrap confidence intervals | 682 Python test functions, 90% test coverage; real model results not yet published |
| [aztdp](https://github.com/Berakhah/Adaptive-Zero-Trust-Defense-Platform--AZTDP-) | Gateway that scores each request's risk and lets OPA decide allow, step-up, revoke or deny, across a 19-service Compose stack | 196 Python test functions; signed-release and SBOM workflow written, not yet run on a tag |
| [selector-drift](https://github.com/Berakhah/selector-drift) | Self-healing extraction for portals with no API; nothing healed is written until it passes a validation gate | 1,434 Python test functions; install still needs a private dependency |

Test counts are Python `def test_` functions, counted on 2026-11-07.

### How I work

- I build with AI pair-programming. The design decisions, reviews and the tests that prove them are mine.
- Measured results state how they were produced and on what sample, in each repo's docs.
- Each README lists what is unfinished.

### Contact

[Portfolio](https://berakhah.github.io) · [LinkedIn](https://www.linkedin.com/in/berekettilahun) · berekettilahun77@gmail.com · [Hire me on Upwork](https://www.upwork.com/freelancers/~01645da719eb4829ed)
