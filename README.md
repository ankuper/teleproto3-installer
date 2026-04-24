# teleproto3-installer

POSIX shell installer, CDN provider plugins, and Cloudflare Worker / Container for [Teleproto3](https://github.com/toxeh/teleproto3) server operators.

---

## Which of these are you?

### 🧑‍💻 "I'm standing up a server"
→ Start at [`docs/quickstart.md`](docs/quickstart.md). One-liner:
```sh
curl -fsSL https://raw.githubusercontent.com/toxeh/teleproto3-installer/main/install.sh | sh
```
The installer emits a secret URL + a Recovery Letter PDF path + systemd status. No interactive prompts on the happy path. Flags for non-defaults: see [`docs/flags.md`](docs/flags.md).

### 🧰 "I'm adding a CDN provider plugin"
→ Start at [`docs/providers.md`](docs/providers.md) and look at [`providers/cloudflare/`](providers/cloudflare/) as a reference. Each provider is a POSIX-sh script implementing a known interface (zone create, DNS record, cert provisioning, edge worker deploy).

### 🔍 "I'm auditing before piping to `sh`"
→ Start at [`docs/verification.md`](docs/verification.md). Each release ships with SHA-256 sums and a detached GPG signature. The installer is POSIX sh, ≤~1500 LoC, no binary blobs executed. Run `shellcheck -x install.sh` to lint.

---

## Scope

- **In scope:** server provisioning, CDN plugin execution, cert acquisition, systemd unit setup, Recovery Letter PDF emission, operator CLI observability bootstrap.
- **Out of scope:** protocol internals (see [`toxeh/teleproto3`](https://github.com/toxeh/teleproto3)), client forks (see `toxeh/tdesktop` / `toxeh/Telegram-iOS` / `toxeh/Telegram`), benchmarking (see [`toxeh/teleproto3-bench`](https://github.com/toxeh/teleproto3-bench)).

## Licence

Apache License 2.0 — see [`LICENSE`](LICENSE).

## Security

Vulnerabilities → [`SECURITY.md`](SECURITY.md).

## Governance

Maintainer and response SLA → [`OWNERSHIP.md`](OWNERSHIP.md). Contributing → [`CONTRIBUTING.md`](CONTRIBUTING.md).
