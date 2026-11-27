# Channels

Tinia agents answer on: WhatsApp by QR code, WhatsApp official API (Meta), Instagram Direct, Messenger, Telegram and the website chat widget. Email, SMS and phone calls are not agent channels today: if the person asks for one, say so plainly and offer the nearest real option (website chat on the site, WhatsApp link in the email signature, Instagram DM). Email can still be collected in the chat and used by the team.

One agent can serve several connections, and Tinia already tells the model which channel it is on. Write channel rules only for what is specific to this business. When one agent serves several channels, label channel-specific instructions ("ON WEBSITE CHAT: …") so the model applies them only there.

## WhatsApp by QR code

- The number is a normal WhatsApp (often the seller's or the company's phone). New contacts may wait for approval before the AI answers (option of the connection); leads from tracked links can be let through.
- Free text any time. Buttons work. Audio from the lead is transcribed; the agent can answer in audio if enabled.
- **Never ask for the WhatsApp number**: you are on it. Email only when there is a reason (proposal, invoice).
- Short messages, one idea each. People read on a phone between other chats.

## WhatsApp official API (Meta)

- Free text only within 24 hours of the lead's last message. Outside it, only approved templates go out (follow-up and campaigns use the template chosen in the connection settings). The agent's replies happen inside the window, so this rarely limits the agent, but never write instructions that promise "I'll message you next week" as free text.
- Buttons and lists work (up to 3 quick replies).
- Same rules as above for contact data.

## Instagram Direct

- The lead often comes from a post, story, reel, ad or a comment rule ("comment PRICE and get it in the Direct"). If they mention it, answer about that. When the first message was sent by a comment rule, do not repeat it.
- DM style: very short, no lists, no formatting, light emojis if the brand uses them.
- Tinia has no phone or email: ask for WhatsApp or email once, when there is real interest and a reason (Tinia already instructs this; add the reason that fits the business, e.g. "para te mandar o orçamento").
- Do not send people to "link in bio" if you can send the link directly.

## Messenger

Like Instagram: chat style, no phone known, ask for contact only with a reason.

## Telegram

The first message may be just /start: greet and ask how you can help. No phone known.

## Website chat widget

- The visitor already saw the widget greeting where the agent introduced itself (it counts as the introduction). **Do not greet or introduce yourself again**; the first reply must already be useful.
- They can leave any second: answer first, short.
- Contact is earned, never a form: the default "optional" mode lets the visitor give contact in the conversation or with the "Deixar contato" button. Ask once, with a reason (send the proposal, continue on WhatsApp if they need to leave), never in the first two replies, never tacked onto the end of every reply.
- If the widget has a WhatsApp connection, tell them they can tap "Continuar no WhatsApp" and keep talking with you there.
- If they mention a page, product or plan of the site, answer about that.
- The visitor's name starts as a placeholder ("Visitante do site · LQ7M"); when they say their name, use it.

## Multichannel agent: a reusable block

```
CHANNEL DIFFERENCES: on WhatsApp you already have the number, never ask for it. On Instagram, Messenger and the website chat, ask for a WhatsApp or email only once, when you have something worth sending (quote, proposal, summary), with that reason in the same sentence. On the website chat the greeting already introduced you: go straight to helping.
```
