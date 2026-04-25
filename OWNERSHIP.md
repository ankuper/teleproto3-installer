# Ownership & Governance

## Maintainer

- **@ankuper** — primary maintainer.

Per-area CODEOWNERS pointers live in `.github/CODEOWNERS` when populated.

## Response SLA

Security reports → 72-hour acknowledgement, 14-day remediation plan (see [`SECURITY.md`](SECURITY.md)).

Other issues → best-effort response.

## Decision-making

- **Installer changes** (`install.sh`, `lib/`): backwards-compatible within a MINOR; breaking changes require MAJOR bump + `CHANGELOG.md` entry.
- **Provider changes** (`providers/<name>/`): each provider versions independently; additive plugins accepted where interface contract is stable.
- **Worker / Container changes** (`worker/`, `container/`): edge-layer parity with spec required; CI enforces fingerprint + anti-probe invariants.

## Relationship to other repos

- [`ankuper/teleproto3`](https://github.com/ankuper/teleproto3) is the normative source for protocol, spec, and reference library. This installer consumes its released artefacts; it does not modify them.
- [`ankuper/teleproto3-bench`](https://github.com/ankuper/teleproto3-bench) exercises servers provisioned by this installer.

## Succession

If @ankuper is unreachable for 90 days, the community may nominate a successor via a GitHub issue; consensus process per the teleproto3 ecosystem governance.
