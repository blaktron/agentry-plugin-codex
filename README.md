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

Codex starts the bundled Agentry MCP server 0.7.16 from `server/` with only
the environment variables listed in `.mcp.json`. Besides the CLI's own settings,
those are the variables the CLI reads keys from by default: `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, `OPENROUTER_API_KEY`, `POE_API_KEY`, `HF_TOKEN`, `VULTR_INFERENCE_API_KEY`, `TYPESAFE_API_KEY`, `YDC_API_KEY`.

A key kept in any other variable does not reach a run started from Codex: a model
key under a variable of your own choosing, a QuickAgent's own secrets, or a target
host's password named with `--host-password`. Keep each where the CLI finds it
without the environment:

- the model key in the OS keychain: `agentry setup --api-key-source keyring` in a
  terminal stores it there;
- a QuickAgent's secrets in its profile: run it once with `agentry run` in a
  terminal, enter them in the guided setup, and keep the profile;
- a target host's sign-in in the OS keychain: the first terminal run offers to
  save it.

Signing in stays in your terminal (`agentry login`). Documentation: https://docs.secureagentry.net/agentry/mcp/.
Privacy: https://secureagentry.net/privacy.
