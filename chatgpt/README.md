# Acorn Harness plugin for ChatGPT and Codex

A portable [Agent Plugins](https://agent-plugins.org) package: the remote Acorn Harness MCP server (`mcp.json`), the `order-wire-harnesses` skill, and the ChatGPT directory listing (`extensions.com.openai` in `plugin.json`). It is what you upload to the OpenAI plugin directory, and Codex can install it from a local marketplace too.

## Connect in ChatGPT

1. Open [chatgpt.com/plugins](https://chatgpt.com/plugins) and click **+**.
2. Choose **Add custom MCP server**.
3. Enter the URL `https://acornharness.com/mcp` and pick no authentication.
4. Click **Create as a plugin**.

## Package for submission

```bash
cd chatgpt
zip -r ../acorn-harness-openai-plugin.zip plugin.json mcp.json skills assets
```

Before uploading, add `privacyPolicyURL` (required by the directory) and, if you have one, `termsOfServiceURL` under `extensions.com.openai.interface`.

The skill is duplicated in `plugins/acorn/skills/`; keep both copies identical.

## Codex without the plugin

See [`codex/`](../codex/).

Questions: support@almond.bot
