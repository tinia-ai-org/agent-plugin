---
name: tinia-daily-review
description: Daily or weekly sales review of a Tinia account with the Tinia MCP tools - sales numbers, hot leads waiting, stuck deals and a short action list. Use when the user asks how sales are going, what to do today, who is waiting, or for a pipeline or team review.
---

# Tinia sales review

Give a sales manager the five-minute review they would otherwise do by opening Tinia. Reply in the user's language, with numbers, names and links to nothing you cannot see. Read-only by default.

## Steps

1. **Numbers.** `get_sales_summary` with `days` = 1 for "today", 7 for "this week", 30 by default. Report new leads, qualified leads (score 8+), deals won with revenue, deals lost, win rate and where new leads came from. Compare with the previous period only if you fetched it.
2. **Pipeline.** `get_pipeline`: leads and value per column. Point out the column where value piles up.
3. **Who needs a person now.** `list_conversations` with `sort` = `score` and `min_score` = 8: hot leads. For the top 5, `get_conversation` to see the last messages and notes, and flag those where the last message is from the lead (waiting for a reply) or the AI handed the lead to a person.
4. **Stuck deals.** `list_conversations` with the negotiation or proposal stage (see stages in `get_pipeline`) sorted by `value`; flag the ones with no activity for days.
5. **Action list.** End with at most 7 actions, one line each: who, what, why (e.g. "Reply to Ana Souza: asked for the price of the annual plan 2 days ago, score 9").

## If the person asks you to act

- Notes (`add_conversation_note`), stage moves (`move_lead_stage`) and closing a deal (`close_deal`) change the account. List exactly what you will change and wait for a yes before doing it. Never close a deal as won without the value the person confirmed.
- You never message leads. To reach a lead, the person replies in Tinia or triggers an automation they already set up (`trigger_automation`, only with a clear yes).
- With the read-only address (`/api/mcp/readonly`) these write tools do not exist; say so instead of trying.
