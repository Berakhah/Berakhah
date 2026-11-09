# Commit identity

Personal email addresses stay out of new commits. GitHub noreply addresses:

- Berakhah: `97037825+Berakhah@users.noreply.github.com`
- Berakhah-sys: `292011954+Berakhah-sys@users.noreply.github.com`

## Set them

In each clone used by the human account:

```bash
git config user.name "Bereket Tilahun"
git config user.email "97037825+Berakhah@users.noreply.github.com"
```

In each clone or agent environment that commits as Berakhah-sys:

```bash
git config user.name "Berakhah-sys"
git config user.email "292011954+Berakhah-sys@users.noreply.github.com"
```

Then, on both accounts, go to GitHub → Settings → Emails and tick **Keep my email addresses private** and **Block command line pushes that expose my email**.

## Credit both accounts: the `Co-authored-by` trailer (from 9 Nov 2026)

Agent commits are authored by @Berakhah-sys, so they don't count on @Berakhah's contribution
graph. The convention from 9 Nov 2026 is that every commit made as @Berakhah-sys ends with:

```
Co-authored-by: Bereket Tilahun <97037825+Berakhah@users.noreply.github.com>
```

Add it automatically with a `commit-msg` hook in each agent clone (or once via a global
`core.hooksPath`). It only touches commits made as Berakhah-sys, adds the trailer once, and
doesn't duplicate it on `--amend`. Tested 9 Nov 2026 with git 2.43.0.

```sh
#!/bin/sh
# .git/hooks/commit-msg  (chmod +x)
[ "$(git config user.email)" = "292011954+Berakhah-sys@users.noreply.github.com" ] || exit 0
git interpret-trailers --in-place --if-exists addIfDifferent \
  --trailer "Co-authored-by: Bereket Tilahun <97037825+Berakhah@users.noreply.github.com>" "$1"
```

### What the trailer does and doesn't do

Checked against GitHub's docs source (github/docs, `profile-contributions-reference.md`,
9 Nov 2026):

- **It does:** name @Berakhah on the commit (both avatars show on it), and the profile's
  *contribution activity* timeline lists "commits you've made or co-authored".
- **It may not:** move the contribution *graph*. For github.com, the docs only promise graph
  credit for commits whose **author** email is on your account. The line "co-authored commits
  must meet the same criteria" is published for GitHub Enterprise Server only. Treat any graph
  change as a bonus and measure it, don't claim it.
- **What reliably counts for @Berakhah today:** pull requests opened by @Berakhah, and the merge
  commits GitHub creates when @Berakhah merges them on the default branch. Agent work that lands
  through PRs opened and merged by this account already shows up that way.

## What this does not fix

Existing commits in agent-perimeter, ground-truth, selector-drift, ledger-sense, AZTDP and this repo still carry the old address. `.mailmap` only changes how `git log` displays them. Removing the address needs a history rewrite and force-push, which is a separate decision.

On 9 Nov 2026 one more slipped through: agent-perimeter commit `286b76b` ("Publish to PyPI as
agent-perimeter-scan") is authored with the personal address, from a desktop session whose clone
wasn't configured. It's on `main` and isn't being rewritten. Run the `git config` lines above in
every new clone before the first commit.

## Proposed About-text changes (not applied)

| Repo | Current | Proposed |
|---|---|---|
| aztdp | "…Docker Compose stack; not production-ready yet." | "Zero-trust reference platform: per-request risk scoring on top of valid JWTs, with OPA deciding allow, step-up, revoke or deny. Runs as a Docker Compose stack." (The README's Status section keeps the caveat.) |
| shopfast-demo | "INTENTIONALLY VULNERABLE demo store … Do not deploy." | Keep. That warning is a safety label, not hedging. |
