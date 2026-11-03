# Acorn Harness in Codex

Connect Codex to the Acorn Harness MCP server to configure, price and order custom XT30, XT30(2+2) and XT30 + JST GH wire harnesses.

## One command

```bash
codex mcp add acorn --url https://acornharness.com/mcp
```

## Or edit config.toml

Add this to `~/.codex/config.toml` (or a trusted project's `.codex/config.toml`); it's also in [`config.toml`](./config.toml):

```toml
[mcp_servers.acorn]
url = "https://acornharness.com/mcp"
```

The server is public Streamable HTTP with no authentication, so there's nothing to log in to. The Codex CLI, IDE extension and desktop app share this file. Run `/mcp` in the Codex TUI (or `codex mcp list`) to check that `acorn` is connected.

Optional: make Codex always ask before creating an order.

```toml
[mcp_servers.acorn.tools.create_order]
approval_mode = "prompt"
```

## Try it

> Quote 10 XT30(2+2) wire harnesses, 350 mm, 16 AWG, end A straight and end B right angle down, then give me a checkout link.

Codex calls `quote_harness`, then `create_order`, and returns a link on acornharness.com where you pay. Codex never needs your card details.

Full setup guide for every assistant: https://acornharness.com/developers#ai · API docs: https://acornharness.com/developers#api

[Privacy Policy](https://acornharness.com/privacy) · [Terms of Service](https://acornharness.com/terms) · Questions: support@almond.bot
