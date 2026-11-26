---
name: tinia-setup
description: Set up or extend a Tinia account with the Tinia MCP tools - draft AI agent, price list, knowledge base, lead capture from ad or website forms, automations (welcome, follow-up, hand-off to a salesperson) and a check of what is missing. Use when the user asks to configure, set up, onboard, automate or "make Tinia work" for their business.
---

# Set up Tinia

Tinia is a WhatsApp sales platform: AI agents answer leads on WhatsApp, Instagram, Messenger, Telegram and website chat, and a CRM (pipeline, contacts, automations) tracks every lead. The `tinia` MCP server gives you the account's tools. Reply in the user's language.

## Rules that never bend

- You never message leads. The account's own AI agent talks to customers. Your tools configure the account and read it.
- Automations you create start **paused**. Call `activate_automation` only after you showed the person the final flow (trigger + each block in plain words) and they said yes in this conversation.
- Lead sources you create start with the first message **off**. Do not promise that the source alone will message the lead: an automation with the `lead_form_received` trigger does that.
- A lead source's webhook address is a secret that never passes through you. Tell the person to open **Settings › Integrations › Lead forms** in Tinia and press **Generate new address** on the source to copy it.
- If a tool answers `insufficient_scope` or a tool is missing, the connection is read only. Tell the person to reconnect with read and write access (only an owner or manager can authorize). Do not look for workarounds.

## Steps

1. **Know the account.** Call `get_account`, then `list_connections`, `list_agents`, `list_lead_sources` and `list_automations`. Summarize in 3 to 5 lines what exists.
2. **Check the basics that only the person can do in the Tinia app** (you cannot do them through MCP):
   - No WhatsApp connection: they connect one at **Connections › New connection** (QR code or official API).
   - The connection has no agent, or automatic reply is off: they link the agent in the connection's settings.
   Say what is missing, then continue with what you can do.
3. **Agent, prices and knowledge (if missing).** Ask for the business facts; never invent prices, policies or promises.
   - `create_agent` makes a DRAFT agent (name, biography, tone, language, instructions, business context). `update_agent` changes a draft or paused agent; an active agent is edited only in Tinia. The person tests the draft in the preview, activates it and links it to a connection.
   - `list_products`, then `create_products` for the price list. Products start inactive: the person reviews and turns them on at **Products**.
   - `add_knowledge_text` for FAQ, policies and product details. Show the text and get a yes first: every agent of the account searches it.
4. **Agree on the goal in one question at most.** Typical: "When a lead fills the Instagram form, welcome them on WhatsApp, ask one qualifying question and hand them to a salesperson."
5. **Lead capture.** For ad or website forms, create one source per channel with `create_lead_source` (`platform`: meta, tiktok, google, pinterest, linkedin, or `other` for website, Google Tag Manager, Zapier or Make) and the WhatsApp `instance_id` from `list_connections`. Then give the person the "Generate new address" instruction above.
6. **Automation.** Build it with `create_automation`. Read the trigger and flow format in the tool description; keep flows short (3 to 6 blocks). For form leads use the trigger `lead_form_received` with `sourceId` of the source you just created. Prefer `send_buttons` or `ask_question` over long texts, and end with a hand-off (transfer) or a notify block so a person follows up.
7. **Check.** Call `get_automation` and read `issues`. Fix them with `update_automation` (the automation is still paused) until there are none.
8. **Confirm and activate.** Show the flow in plain words, block by block, with the exact texts the lead will receive. Only after a clear yes, call `activate_automation`.
9. **Close with a short list**: what you created (with names), what the person still has to do in the app (activate the agent and products, address of the source, connection), and how to test it (fill the form with their own phone).

## Good defaults

- Message texts: short, friendly, one question per message, in the language of the business. Use `{{primeiro_nome}}` (first name) when available.
- Do not create duplicates: reuse a source or automation with the same purpose and update it (pause first if it is active).
- Never activate more than one automation for the same trigger and source without asking.
