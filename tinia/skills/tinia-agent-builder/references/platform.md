# How a Tinia agent works

## Contents
1. Fields and limits
2. What Tinia adds to the prompt by itself
3. Account-level pieces every agent uses
4. Options set only in the app
5. Runtime tools the agent has during a conversation
6. Lifecycle

## 1. Fields and limits

What `create_agent` / `update_agent` accept (the same fields as Agents › Edit in the app):

| Field | Limit | Goes into the prompt as |
|---|---|---|
| name | 1 to 100 chars (persona name cut at 50) | "Você é {name}, um assistente de vendas especializado." First line of the system prompt |
| biography | up to 1000 chars | Right after the first line. Sets voice and identity |
| tone | professional, friendly, formal, casual | A tone line (friendly and casual allow emojis) |
| verbosity | concise, balanced, detailed | Length rule: concise = 1 to 2 sentences, balanced = 2 to 3, detailed = up to 5 short paragraphs |
| language | pt-BR, en, es, id, ru, ur, de, fil, tr, ar, it (en-US still accepted) | Main language. Default pt-BR |
| instructions | up to 30 items, each up to 1000 chars; the whole list is replaced on update | "## INSTRUÇÕES PRIORITÁRIAS DO AGENTE", marked as highest priority, in the order given |
| business.company_name, industry, description (1000), target_audience (500), website, products (up to 50 short names) | | "## Contexto do Negócio" in the user prompt |

Not reachable through MCP but present on agents built in the app: `personality.objectives` (a numbered "## Objetivos" list), language mode and allowed languages, `interactive_config` (section 4) and `model_config`.

MCP creates agents with the platform default model on OpenRouter (temperature 0.7, 1024 max tokens). The person can change model and provider in Agents › Modelo. For sales chat, a fast model is fine; for long technical or consultative sales (B2B, APIs, many plans) suggest a stronger model and temperature 0.5 to 0.6 (the best agent on the platform uses gpt-4.1 at 0.6, 700 tokens).

An agent can be activated only with a biography, an active instruction or business context. An empty agent answers as a generic "Assistente".

## 2. What Tinia already adds (do not repeat it)

Every reply prompt already contains:

- **"Como um bom vendedor responde"**: length rule from verbosity; reread the conversation and cite what the lead said; answer first, then at most one question or a concrete next step, and not every message ends in a question; never ask what was answered or repeat a question; qualify (need, size, decision maker, timing) gradually, never as a form; ask for contact only with a reason that benefits the lead, once; never invent products, prices, deadlines or conditions; empathy with objections; write like a person, no stock phrases; line breaks.
- **"## Canal"**: which channel. Outside WhatsApp: DM style, no promises to call or send on WhatsApp without the number, and a rule to ask for WhatsApp or email once when there is real interest (only while Tinia has neither).
- **Lead memory** ("O que você já sabe deste lead"): first name, company, role, city, pipeline stage, BANT score and evidence, conversation summary, objections, interests, deal value, paid orders, last internal notes.
- **Conversation state**: whether the agent already introduced itself (on website chat the widget greeting counts), the questions it already asked, the contact data it already has, how many messages in a row the lead sent. Several lead messages in a row get one combined reply.
- **Knowledge base** passages and the **price list** (active products, with photo and link) relevant to the message.
- **Language line**: reply in the lead's language when the mode is automatic.
- A final guard removes a question that repeats one of the last three, and replaces any claim of a booked meeting that the calendar does not have.

So the instructions you write are for what is specific: the goal and next step, the facts, the qualification questions that matter for this business, objections with the company's real answers, when to hand off, what is out of scope, and style details that differ from the default.

## 3. Account-level pieces every agent uses

- **Price list** (Products): name, price, unit, aliases, photo, link, repurchase cycle. The agent quotes only active products and computes the deal value from what the lead asks for. `create_products` adds them inactive.
- **Knowledge base**: PDF, DOCX or text, searched per message (semantic + keyword, about 6 passages). Best for FAQs, policies, technical specs, scripts. Write knowledge text as short headed sections with one fact per line; that is how it is chunked (about 1200 characters per passage).
- **Objection playbook** (Settings › Members): used by the next-step and coaching features, not yet by the reply agent. Put the objections the agent must handle in its instructions.

## 4. Options set only in the app (Agents › the agent)

Tell the person which to turn on for the archetype:

- **Buttons** (quick replies and action buttons: website, booking link, call the seller), **media** (send shareable knowledge documents), **product photos** (on by default), **location**.
- **Hand-off**: "when the lead asks for a person" (on by default) and "when the lead is ready to buy" (off by default).
- **Follow-up of silent leads**: off by default; 1 to 3 attempts after about 20 h, 2 days, 3 days, only 9h to 20h.
- **Audio reply** when the lead sends audio (needs an OpenAI key).
- **Language**: automatic (answer in the lead's language among the allowed ones) or fixed.
- **Copilot vs autopilot** is per connection: in copilot the agent only suggests.
- **Payment links** (Asaas) with "the AI may send a link" and a maximum amount; **calendar** (Google, Outlook or Calendly) for booking.

## 5. Runtime tools during a conversation

The agent decides these by itself; your instructions say when:

- **transfer_to_human**: passes the conversation to the lead's owner or the next seller in rotation and pauses the AI. It carries a summary for the team that the lead never sees. Instructions must say when to use it, what goes in the summary, and what to tell the lead (one sentence).
- **schedule_meeting**: books in the connected calendar; only its confirmation text counts as booked. With Calendly connected, the agent sends the Calendly link instead.
- **send_payment_link**: only with the option on and under the maximum amount; above it, the agent hands off.

## 6. Lifecycle

draft → (person tests in preview, activates) → active → paused. MCP edits only draft and paused agents. One agent per connection; an agent can serve several connections. The preview in the app runs the same prompt, knowledge, prices, channel rules, buttons and calendar as production without sending or booking, and has a channel selector: always tell the person to test there on the target channel.
