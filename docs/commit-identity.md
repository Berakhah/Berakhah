# Commit identity (steps not yet run)

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

## What this does not fix

Existing commits in agent-perimeter, ground-truth, selector-drift, ledger-sense, AZTDP and this repo still carry the old address. `.mailmap` only changes how `git log` displays them. Removing the address needs a history rewrite and force-push, which is a separate decision.

## Proposed About-text changes (not applied)

| Repo | Current | Proposed |
|---|---|---|
| Adaptive-Zero-Trust-Defense-Platform--AZTDP- | "…Docker Compose stack; not production-ready yet." | "Zero-trust reference platform: per-request risk scoring on top of valid JWTs, with OPA deciding allow, step-up, revoke or deny. Runs as a Docker Compose stack." (The README's Status section keeps the caveat.) |
| shopfast-demo | "INTENTIONALLY VULNERABLE demo store … Do not deploy." | Keep. That warning is a safety label, not hedging. |
