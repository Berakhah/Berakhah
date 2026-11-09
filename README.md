## Bereket Tilahun

**Security engineer for AI-built apps.** I audit Supabase row-level security in apps made with Lovable, Bolt, Cursor and Next.js, I test MCP servers and tool-using agents, and I write Python that fails closed. Based in Addis Ababa.

### Flagship work

| Project | What it is | One proof point |
|---|---|---|
| [**agent-perimeter**](https://github.com/Berakhah/agent-perimeter) | Security scanner for MCP servers and agents: SARIF output, a GitHub Action, and `uv tool install agent-perimeter-scan` | Passive census of the whole official MCP Registry (31,953 entries, 14 Sep 2026); every published figure is reproducible from `records.csv` |
| [**shopfast-demo**](https://github.com/Berakhah/shopfast-demo) | Intentionally vulnerable Next.js + Supabase + Stripe store, with a sample audit report | 12 planted flaws (3 Critical, 6 High, 3 Medium); CI reproduces 10 of them on every push |
| [**ground-truth**](https://github.com/Berakhah/ground-truth) | Eval harness for LLM field extraction on invoices and pay applications | Headline numbers are recomputed from published per-item verdicts by a stdlib-only script. No real provider results yet; the README says so |

### Writing

[0 of 302: what a full census of the MCP Registry says about the 2026-07-28 revision](https://berakhah.github.io/writing/mcp-registry-census.html) · [Twelve ways an AI-built Supabase + Stripe store leaks customer data](https://berakhah.github.io/writing/shopfast-twelve-leaks.html) · [I deleted a census tier I'd already built](https://berakhah.github.io/writing/scope-files-vs-random-sampling.html)

### Hire me for

1. **Supabase RLS and storage audit:** can one customer read another customer's rows, files or Realtime messages? See ShopFast SF-02, SF-09, SF-10 and SF-11.
2. **Payments trust audit:** leaked service-role or Stripe keys, unverified webhooks, prices taken from the browser. See ShopFast SF-01, SF-03, SF-05 and SF-06.
3. **AI feature and agent audit:** chat endpoints without limits, and tools that act on a model-supplied id instead of the signed-in user. See ShopFast SF-08 and SF-12, and agent-perimeter for MCP servers.

Every finding comes with a reproduction and the code fix, like the [ShopFast sample report](https://github.com/Berakhah/shopfast-demo#how-id-audit-your-app). Book through [Upwork](https://www.upwork.com/freelancers/~01645da719eb4829ed).

### How I work with AI agents

Most commits in my 2026 repos come from [@Berakhah-sys](https://github.com/Berakhah-sys), the second account my AI coding agents commit through. I design the systems, write the specifications with Claude Code, set the evaluation criteria, and review and test the changes; Claude Code generates a substantial part of the code under my direction. From 9 Nov 2026 the convention is that those commits also carry a `Co-authored-by` trailer for this account ([how and why](docs/commit-identity.md)). Each repo's README says how it was built and what isn't finished.

[berakhah.github.io](https://berakhah.github.io) · [Upwork](https://www.upwork.com/freelancers/~01645da719eb4829ed) · [LinkedIn](https://www.linkedin.com/in/berekettilahun)
