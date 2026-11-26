# Tinia

Set up and run [Tinia](https://tinia.com.br), the WhatsApp sales platform with AI agents and a CRM, from Claude Code or Codex.

## What it includes

- **MCP server** `https://tinia.com.br/api/mcp`. You sign in with your Tinia account (OAuth). Only an owner or manager of the account can authorize it, and they choose read-only or read and write access.
- **Skill `tinia-setup`**: from a plain request, it sets up lead capture, automations, a draft agent, a price list and knowledge base text. It checks what is missing and activates only after you confirm.
- **Skill `tinia-daily-review`**: sales numbers, hot leads waiting, stuck deals and a short action list.

## Safety

- The MCP server never sends messages to leads.
- Automations start paused, agents start as drafts and products start inactive. Turning an automation on needs its own permission, and agents and products are activated only in the Tinia app.
- To try it without risk, use the read-only address `https://tinia.com.br/api/mcp/readonly`, which only exposes query tools.
- Access can be removed at any time in Tinia under API keys › Use with AI (MCP).

## Links

[Connect your AI](https://tinia.com.br/conectar-ia) · [Privacy](https://tinia.com.br/privacy) · [Terms](https://tinia.com.br/terms)
