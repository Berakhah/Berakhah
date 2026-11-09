# Growth plan (drafted 9 Nov 2026)

Private working notes made public on purpose: the goal is credibility you can check. Nothing here has been done yet unless it says so.

## 1. Upstream contribution targets

Each idea needs checking against the project's current issue tracker before opening anything; none has been filed.

| # | Target | First issue/PR idea | Why it fits |
|---|---|---|---|
| 1 | `modelcontextprotocol/python-sdk` | Fail-closed `tools/list` pagination: a test plus a fix if the client accepts a repeated `nextCursor` or a page with no `tools` key. agent-perimeter already treats both as an incomplete listing (exit 2) | Fail-closed Python; the behaviour is already specified and tested in agent-perimeter |
| 2 | `modelcontextprotocol/registry` (or the docs) | Docs PR: what "remote-only" means for consumers, using the census finding that 56% of entries have no fetchable artifact | Census data is published and reproducible |
| 3 | `supabase/supabase` docs (RLS / Storage guides) | A short "common mistakes" note: a `SECURITY DEFINER` RPC bypassing RLS, a storage bucket readable by any signed-in user, Realtime with `using (true)` (ShopFast SF-09/10/11) | Each one has a runnable proof in shopfast-demo |
| 4 | `OWASP/www-project-top-10-for-large-language-model-applications` | A concrete example for excessive agency / insecure tool use: a tool acting on a model-supplied id (ShopFast SF-12), with the fix | A worked example with a proof of concept |
| 5 | `semgrep/semgrep-rules` | A rule for Next.js/Supabase: `createClient` called with a `NEXT_PUBLIC_*SERVICE_ROLE*` key (ShopFast SF-01), with true- and false-positive test files | Small and reviewable; it targets the most common AI-app leak |

## 2. agent-perimeter launch checklist

Don't start until agent-perimeter PR #7 is merged, its CI is green, the 3 fixture alerts are dismissed, and the GIF is recorded.

- [ ] Record `docs/demo/scan.gif` with `vhs docs/demo/scan.tape` (needs Docker) and add it to the README hero
- [ ] Decide on PyPI. If yes: trusted publisher, `pypi` environment, version bump, run `pypi.yml`
- [ ] Tick "Publish to Marketplace" on the next release (branding is already set)
- [ ] Site write-up on berakhah.github.io: census method, the 0/302 result with its Wilson interval, what it does **not** show (remote-only entries, no live probes), and how to reproduce it
- [ ] **Show HN:** title "Show HN: Agent Perimeter – reproducible security scans for MCP servers". The first comment covers the census number, the caveats and the AI-assisted disclosure
- [ ] **r/netsec:** post the write-up rather than the repo (the sub prefers technical content); link the repo at the end
- [ ] **MCP community Discord:** share in the appropriate showcase channel after reading its self-promotion rules
- [ ] Answer every comment for 48 hours; turn reproducible bug reports into issues

## 3. Blog titles from existing findings

1. **"0 of 302: what a full census of the MCP Registry says about the 2026-07-28 revision"**: the method, the Wilson interval, and why zero isn't "none".
2. **"Twelve ways an AI-built Supabase + Stripe store leaks customer data, each with a proof you can rerun"**: the ShopFast findings, grouped by root cause.
3. **"I deleted a census tier I'd already built: scope files versus random sampling"**: why the live-discover stratum couldn't satisfy the never-probe-without-authorisation rule.
