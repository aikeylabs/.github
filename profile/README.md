<div align="center">

# AiKey Labs

**One workbench for every AI tool.**

Unify keys, accounts, and routing for Claude, Codex, and Kimi —
so your team can swap quotas, watch costs, and orchestrate
multi-model productivity without breaking flow.

**English** · [中文](README.zh.md)

<p>
  <a href="https://github.com/aikeylabs/launch/releases/latest"><img alt="latest release" src="https://img.shields.io/github/v/release/aikeylabs/launch?label=latest&style=flat-square"></a>
  <a href="https://github.com/aikeylabs/launch#install"><img alt="quickstart" src="https://img.shields.io/badge/quickstart-launch-2563eb?style=flat-square"></a>
  <img alt="platforms" src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-555?style=flat-square">
  <img alt="status" src="https://img.shields.io/badge/status-GA-22c55e?style=flat-square">
</p>

</div>

---

## Install in one line

**macOS / Linux**

```bash
curl -fsSL https://github.com/aikeylabs/launch/releases/latest/download/latest-install.sh | sh
```

**Windows (PowerShell, native — no WSL required)** — see the
[Windows installer notes](https://github.com/aikeylabs/launch#windows-specific) in `launch`.

After install, open a new terminal and run `aikey web` to add your first key.

---

## Why AiKey?

<table>
<tr>
<td width="50%" valign="top">

### One vault for all your AI credentials

Import Claude / Codex / Kimi API keys and OAuth accounts once.
Real credentials stay in the local vault — daily work only sees
revocable route tokens or the currently active binding.

```bash
aikey add my-key
aikey auth login claude
aikey use
```

</td>
<td width="50%" valign="top">

### Live cost & token insight

Per-key, per-account, per-protocol usage trends plus token
structure (cache share, request volume, provider mix). Catch the
spike before the invoice does.

```bash
aikey web        # Vault · Usage · Dashboard
```

</td>
</tr>
<tr>
<td width="50%" valign="top">

### Multi-window, multi-account in parallel

Claude in window A, Codex in window B, Kimi in window C —
each terminal can run a different account without colliding
on shared environment variables.

```bash
aikey activate claude2   # current terminal only
```

</td>
<td width="50%" valign="top">

### Quota-out without breaking flow

When the active account runs out mid-conversation, don't exit
your `claude` session. Switch the binding, and the next request
picks up the new account.

```bash
aikey use backup-account
```

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### Custom routing for any AI client

`aikey route` outputs a `base_url` + `api_key` you can paste into Cursor, OpenCode,
Continue, or any OpenAI / Anthropic-compatible client. Compose multiple accounts
into one controllable routing fabric.

```bash
aikey route                # list every available route
aikey route my-key         # copy base_url + api_key for a specific key
```

</td>
</tr>
</table>

For the full walkthrough with screenshots, see
**[launch · Quickstart →](https://github.com/aikeylabs/launch)**.

---

## Projects

| Repository | What it is |
|---|---|
| **[launch](https://github.com/aikeylabs/launch)** | Cross-platform installers, release bundles, Quickstart for macOS / Linux / Windows. **Start here.** |
| **[aikey-cli](https://github.com/aikeylabs/aikey-cli)** | The `aikey` / `ak` command-line tool — vault, OAuth login, key switching, route, doctor, test. Rust. |
| **[aikey-proxy](https://github.com/aikeylabs/aikey-proxy)** | Local proxy routing Claude / Codex / Kimi traffic by virtual key, capturing usage and cost. Go. |

> More sub-projects (VS Code extension, browser extension, team-edition control panel) will be opened up as they reach GA.

---

## Daily commands

```bash
aikey list              # All keys in the vault
aikey use               # Switch the active key
aikey route             # Show base_url + api_key for any client
aikey web               # Open the local console (vault, usage, dashboard)
aikey doctor            # One-click health check
aikey test --all        # Probe every credential
```

The CLI also responds to the short alias `ak` (`ak use`, `ak env`, `ak doctor`).

---

## Documentation

- [Quickstart](https://github.com/aikeylabs/launch#aikey-quickstart) — end-to-end personal-edition flow
- [Daily commands](https://github.com/aikeylabs/launch#daily-commands) — full command list
- [Third-party clients](https://github.com/aikeylabs/launch#advanced-use-keys-in-third-party-ai-clients) — Cursor / OpenCode / Continue
- [Troubleshooting](https://github.com/aikeylabs/launch#troubleshooting) — common issues

---

## Community

- **Issues & feature requests** — file in the relevant sub-project repo above
- **Security disclosures** — please report privately (see each repo's `SECURITY.md`)
- **Contributions welcome** — please follow each project's contributing guide

<div align="center">
  <sub>AiKey Labs — centralize sensitive credentials, distribute work entrypoints freely.</sub>
</div>
