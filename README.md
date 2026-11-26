# Tinia plugin for AI assistants

Plugin that connects Claude Code and Codex (and other apps that read Agent Plugins) to Tinia, the WhatsApp sales platform with AI agents and a CRM. It bundles the remote MCP server (`https://tinia.com.br/api/mcp`, OAuth sign-in with the user's Tinia account) and two skills:

- `tinia-setup`: sets up lead capture and automations from a plain request, checks what is missing and only activates after the person confirms.
- `tinia-daily-review`: sales numbers, hot leads waiting, stuck deals and an action list.

The plugin connects to the full MCP at `https://tinia.com.br/api/mcp`. The MCP server never sends messages to leads. Automations created through it start paused, and a separate permission is needed to turn them on. To test without risk, use the read-only address `https://tinia.com.br/api/mcp/readonly` (same sign-in, only query tools). Without the plugin, either server can be added by hand (`claude mcp add --transport http tinia https://tinia.com.br/api/mcp`, `codex mcp add tinia --url https://tinia.com.br/api/mcp`).

## Layout

```
.claude-plugin/marketplace.json   # Claude Code marketplace (this folder as the repo root)
.agents/plugins/marketplace.json  # Codex marketplace
tinia/
  .claude-plugin/plugin.json      # Claude Code manifest
  plugin.json                     # Codex / Agent Plugins manifest
  .mcp.json                       # MCP for Claude Code (type http)
  mcp.json                        # MCP for Codex (type streamable-http)
  skills/<name>/SKILL.md          # shared skills
```

## Install

```bash
claude plugin marketplace add tinia-ai-org/agent-plugin
claude plugin install tinia@tinia
```

In Claude Code you can also run `/plugin marketplace add tinia-ai-org/agent-plugin`.

Codex: `codex plugin marketplace add tinia-ai-org/agent-plugin`, then install `tinia` from it.

## Publishing

License: MIT (`LICENSE`, also inside `tinia/`).

This repository is the public plugin at `https://github.com/tinia-ai-org/agent-plugin`. From the repo root:

1. Run `claude plugin validate ./tinia`.
2. Claude: submit at claude.ai/directory/manage as a plugin bundle (plugin path `tinia`), and the server URL as an MCP connector.
3. ChatGPT and Codex: submit the plugin in the OpenAI plugin directory (needs the remote https MCP; no hooks).

The tool names in the skills are kept in sync with Tinia's MCP.
