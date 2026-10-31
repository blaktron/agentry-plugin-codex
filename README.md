# Agentry for Codex

Agentry brings QuickAgents into your agent host. Search a registry, read a QuickAgent's capability contract, scan findings and signature, install it, and run it in Agentry's sandboxed runner with a preview you approve first. Build your own QuickAgent, validate it, get an AI Review and test it before you publish. The plugin drives the Agentry CLI on your computer; the CLI keeps your sign-in and enforces each QuickAgent's contract.

## Install

```sh
codex plugin marketplace add blaktron/agentry-plugin-codex
codex plugin add agentry@agentry
```

Then ask Codex to "check that Agentry is set up".

## Requirements

- The Agentry CLI 0.6.63 or newer on `PATH` (or `AGENTRY_BIN` set to it). Install it from https://secureagentry.net/download.
- Node 24 or newer on `PATH`.
- Docker, for runs on this computer.

Codex starts the bundled Agentry MCP server 0.6.1002 from `server/` with only
the environment variables listed in `.mcp.json`; no credential is passed to it.
Signing in stays in your terminal (`agentry login`). Documentation: https://docs.secureagentry.net/agentry/mcp/.
Privacy: https://secureagentry.net/privacy.
