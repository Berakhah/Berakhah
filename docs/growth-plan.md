# Growth plan (drafted 9 Nov 2026, status updated the same evening)

Private working notes made public on purpose: the goal is credibility you can check. Each item says
whether it's done, and what checking it turned up.

## 1. Upstream contribution targets

Checked on 9 Nov 2026 against each project's current tracker and CONTRIBUTING. **Nothing has been
filed yet.** The drafts and exact steps are kept outside this repo.

| # | Target | Original idea | What the check found | Next step |
|---|---|---|---|---|
| 1 | `semgrep/semgrep-rules` | Rule: `createClient` with a `NEXT_PUBLIC_*SERVICE_ROLE*` key | **Already proposed** by someone else: open PR #4057. It fails the repo's own CWE metadata lint (CWE-200) and misses three variants | Review #4057 with the fix and test cases instead of opening a duplicate |
| 2 | `modelcontextprotocol/python-sdk` | Fail-closed `tools/list` pagination | **No code gap:** a missing `tools` key already raises, and the SDK has no public cursor loop. **The docs have the gap:** two documented `while True` pagination loops never stop on a repeated cursor | Issue first. CONTRIBUTING closes outside PRs unless a maintainer assigns the issue; a docs fix with two tests is ready |
| 3 | `modelcontextprotocol/registry` docs | What "remote-only" means for consumers | Confirmed: "Security Scanning" delegates to package registries, which never see remote-only entries (56% on 14 Sep 2026) | Issue, then a one-sentence docs PR |
| 4 | `supabase/supabase` docs | "Common mistakes": SECURITY DEFINER, storage, Realtime | **Narrowed:** the first two are already documented. The Postgres Changes quickstart's `using (true)` policy has no warning that it streams every row to every subscriber (ShopFast SF-10) | Issue, then a six-line caution admonition |
| 5 | OWASP LLM Top 10 | Worked excessive-agency example | **The repo moved:** the old one is a legacy archive. The active one is `GenAI-Security-Project/GenAI-LLM-Top10`, where Excessive Agency is **LLM03:2026** and the release is final | Release-feedback issue proposing a scenario where a tool acts on a model-chosen order id (SF-12) |

Best route to a merged PR in a project buyers recognise: Supabase (4), then python-sdk (2) if a
maintainer assigns the issue.

## 2. agent-perimeter launch checklist

- [x] `docs/demo/scan.gif` recorded on a runner from `scan.tape` (`demo-gif.yml`), now the README hero
- [x] PyPI through trusted publishing: **`agent-perimeter-scan` 1.2.1**. PyPI refused `agent-perimeter` as too close to an existing project. The command and the Action keep their names
- [x] v1.2.0 and v1.2.1 released; `v1` follows 1.2.1
- [x] Publish to Marketplace ticked on the release (done in a browser session; listing page not yet confirmed from here)
- [x] `examples/scan-reference-server.yml`, run by CI on every change
- [x] Census write-up published (section 3)
- [ ] **Show HN:** "Show HN: Agent Perimeter – reproducible security scans for MCP servers". The first comment covers the census number, the caveats and the AI-assisted disclosure
- [ ] **r/netsec:** post the census write-up rather than the repo
- [ ] **MCP community Discord:** share in the showcase channel after reading its rules
- [ ] Answer every comment for 48 hours; turn reproducible bug reports into issues

## 3. Write-ups (published 9 Nov 2026)

1. [0 of 302: what a full census of the MCP Registry says about the 2026-07-28 revision](https://berakhah.github.io/writing/mcp-registry-census.html). The method, the Wilson interval, why zero isn't "none", and the 18 SDK-2.x packages that could move the share to about 6%.
2. [Twelve ways an AI-built Supabase + Stripe store leaks customer data, each with a proof you can rerun](https://berakhah.github.io/writing/shopfast-twelve-leaks.html). The ShopFast findings, grouped by root cause.
3. [I deleted a census tier I'd already built: scope files versus random sampling](https://berakhah.github.io/writing/scope-files-vs-random-sampling.html). Why the live-discover stratum couldn't satisfy the never-probe-without-authorisation rule.

## 4. Measures, tracked monthly

Real numbers, including the small ones. The baseline was taken 9 Nov 2026, before any launch post.

| Date | Stars (6 pinned repos, total) | Followers | Unique cloners, agent-perimeter (14 days) | PyPI installs | Upwork inquiries citing GitHub | Merged upstream PRs |
|---|---|---|---|---|---|---|
| 9 Nov 2026 | 0 | 3 | not yet read | 0 (published that day) | 0 | 0 |

Cloner counts are in each repo's Insights → Traffic; GitHub keeps 14 days, so read them on the
same day each month.

## 5. Profile settings

- **Include private contributions: recommended on** (Settings → Public profile → Contributions & activity). The private repos (`backoffice-kit` and client work)
  hold real effort that the graph doesn't show. GitHub shows only daily counts from them, never
  repo names or details. Don't cite those counts as evidence; they can't be checked.
- One headline everywhere: **"Security engineer for AI-built apps"**. Done in the profile README,
  on the site (title, footer, hero) and in the Upwork title (9 Nov). The GitHub bio still needs changing.
