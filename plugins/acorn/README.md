# Acorn Harness plugin for Claude Code

Connects Claude Code to the Acorn Harness MCP server (`https://acornharness.com/mcp`) and adds an `order-wire-harnesses` skill, so Claude can configure, price and order custom XT30, XT30(2+2) and XT30 + JST GH wire harnesses.

## Install

Inside Claude Code:

```
/plugin marketplace add almond-bot/acorn-plugins
/plugin install acorn@acorn-plugins
```

Or from a shell:

```bash
claude plugin marketplace add almond-bot/acorn-plugins
claude plugin install acorn@acorn-plugins
```

Run `/mcp` to confirm `plugin:acorn:acorn` is connected.

Just want the MCP server, without the plugin?

```bash
claude mcp add --transport http acorn https://acornharness.com/mcp
```

## What's inside

| File | Purpose |
| --- | --- |
| `.claude-plugin/plugin.json` | Plugin manifest. |
| `.claude-plugin/icon.png` | Plugin icon. |
| `.mcp.json` | The remote MCP server (Streamable HTTP, no auth). |
| `skills/order-wire-harnesses/SKILL.md` | How to turn a request into a design, quote it, and hand the buyer a checkout link. |

The marketplace that lists this plugin is `.claude-plugin/marketplace.json` at the repository root.

## Develop

```bash
claude plugin validate ./plugins/acorn
claude plugin validate .            # the marketplace
claude --plugin-dir ./plugins/acorn
```

The skill is duplicated in `chatgpt/skills/`; keep both copies identical.

Questions: support@almond.bot
