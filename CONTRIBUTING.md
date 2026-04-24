# Contributing to teleproto3-installer

Thanks for your interest.

## What lives where

- `install.sh` — entrypoint. POSIX sh, no bashisms. Single file.
- `lib/` — shared shell helpers (argument parsing, logging, platform detection, systemd integration).
- `providers/` — CDN provider plugins. One subdirectory per provider; each implements a known interface (see [`docs/providers.md`](docs/providers.md)).
- `worker/` — Cloudflare Worker source (TypeScript). Deployed by the `cloudflare` provider.
- `container/` — Cloudflare Container source. Deployed by the `cloudflare` provider.
- `docs/` — operator-facing documentation, provider specs, verification guide.
- `tests/` — POSIX shell tests (bats-style) + `shellcheck` CI.

## Ground rules

- **POSIX sh strictly.** No bashisms in `install.sh` or `lib/`. Validate with `checkbashisms` + `shellcheck --shell=sh`.
- **No interactive prompts on the happy path.** The installer must complete in one invocation without asking questions. Non-default behaviour is behind flags.
- **Plain-text stdout.** No ASCII art, no emoji, no progress bars. Status prefixes `[ok]` / `[warn]` / `[err]` / `[info]` per the CLI output pattern (see `toxeh/teleproto3` architecture §12.6).
- **Zero telemetry.** The installer does not phone home. Ever.
- **Deterministic secret output.** Same inputs → same secret URL format. Recovery Letter PDF generated from Typst source (sourced from `toxeh/teleproto3/spec/ux-tokens/pdf/recovery-letter.typ`).

## PR scope

Keep PRs focused on one of: `install.sh`, one provider, the worker, the container, docs, or tests. Cross-cutting changes are fine but split commits by concern.

## Releases

SemVer. Tags `vX.Y.Z`. Each release attaches: (a) `install.sh` as a standalone artefact, (b) SHA-256 sums, (c) detached GPG signature. The pipe-to-sh URL in README always points to `main` — auditors pin specific tags.
