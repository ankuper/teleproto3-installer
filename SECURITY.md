# Security Policy

teleproto3-installer is an anti-censorship project. We take security reports seriously.

## Reporting a vulnerability

**Do not open a public issue for suspected vulnerabilities.**

Use GitHub's private vulnerability reporting flow on this repository, or coordinate with the `toxeh/teleproto3` security contact (see [that repo's `SECURITY.md`](https://github.com/toxeh/teleproto3/blob/main/SECURITY.md)).

Include:
- A description of the issue and its expected impact.
- Reproduction steps or a proof-of-concept.
- The affected component (`install.sh`, a specific provider, the worker, the container) and release tag where known.

We aim to acknowledge within **72 hours** and to provide a remediation plan or public advisory timeline within **14 days** of acknowledgement.

## Scope

In scope:
- Installer defects that expose operator credentials, leak secrets, or weaken the threat model documented in [`toxeh/teleproto3/spec/threat-model.md`](https://github.com/toxeh/teleproto3/blob/main/spec/threat-model.md).
- CDN provider plugin defects that misconfigure a zone in a security-relevant way.
- Worker / Container defects that break the edge-layer invariants (TLS termination, fingerprint parity, anti-probe behaviour).
- Supply-chain issues in the pipe-to-sh distribution path.

Out of scope:
- Vulnerabilities in upstream CDN provider APIs — report to the provider.
- Vulnerabilities in the Teleproto3 protocol itself — report to [`toxeh/teleproto3`](https://github.com/toxeh/teleproto3).
- Vulnerabilities in client forks — report to the respective fork.

## Disclosure

We prefer coordinated disclosure. Once a fix is in a tagged release, we publish a security advisory on the GitHub Security tab with CVE assignment where appropriate.
