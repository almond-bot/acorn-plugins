# acorn-plugins

Acorn Harness plugins for Claude Code, Codex and ChatGPT: order custom XT30 wire harnesses from AI assistants.

[Acorn Harness](https://acornharness.com) builds custom XT30, XT30(2+2) and XT30 + JST GH wire harnesses to order, for robots, actuators, batteries and power boards. Describe the cable you need and your assistant turns it into a design, quotes the exact price, and gives you a checkout link on acornharness.com. You pay and enter the shipping address there, never in the chat. Every wire harness is Assembled in the USA, 100% continuity tested, and ships within 5 business days (US only).

All of these connect to the same remote MCP server: `https://acornharness.com/mcp` (Streamable HTTP, no authentication).

## Claude Code

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

Run `/mcp` to confirm `plugin:acorn:acorn` is connected. The plugin adds the MCP server and an `order-wire-harnesses` skill. To add only the MCP server:

```bash
claude mcp add --transport http acorn https://acornharness.com/mcp
```

## Codex

```bash
codex mcp add acorn --url https://acornharness.com/mcp
```

Or add this to `~/.codex/config.toml` (or a trusted project's `.codex/config.toml`):

```toml
[mcp_servers.acorn]
url = "https://acornharness.com/mcp"
```

See [`codex/`](./codex/) for more.

## ChatGPT

1. Open [chatgpt.com/plugins](https://chatgpt.com/plugins) and click **+**.
2. Choose **Add custom MCP server**.
3. Enter the URL `https://acornharness.com/mcp` and pick no authentication.
4. Click **Create as a plugin**.

The plugin package for the OpenAI plugin directory is in [`chatgpt/`](./chatgpt/).

## Claude.ai

Custom connectors need a paid Claude plan.

1. Go to **Customize** → **Connectors** → **Add** → **Custom** → **Web**.
2. Enter the URL `https://acornharness.com/mcp`.
3. Choose **No sign-in** and save.

## Try it

> Quote 10 XT30(2+2) wire harnesses, 350 mm, 16 AWG, straight on one end and right angle down on the other.

> I need 4 XT30 pigtails, 200 mm of 18 AWG with tinned leads. Send me a checkout link.

> Make a 600 mm XT30(2+2) to JST GH CAN cable with the signal pair crossed and order 2.

## Repository layout

| Path | What it is |
| --- | --- |
| `.claude-plugin/marketplace.json` | Claude Code marketplace `acorn-plugins`, listing the `acorn` plugin. |
| `plugins/acorn/` | Claude Code plugin: manifest, icon, `.mcp.json` and the ordering skill. |
| `codex/` | Codex `config.toml` snippet and setup notes. |
| `chatgpt/` | Agent Plugins package for ChatGPT and the OpenAI plugin directory. |
| `server.json` | Official MCP Registry entry (`com.acornharness/acorn`). |

Full setup guide for every assistant: https://acornharness.com/ai

Questions: support@almond.bot

## License

[MIT](./LICENSE)
