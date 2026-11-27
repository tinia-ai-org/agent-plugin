# Agent blueprints

Each blueprint gives: the goal and success event, the instruction set to write (labels in order), when to hand off, the app options to turn on, and the bench scenarios that matter most. Adapt the content to the business; keep the structure.

## Contents
- A. Sales (SDR / consultative)
- B. Closer / e-commerce and catalog
- C. Qualification and routing (BANT)
- D. Support / customer service (SAC)
- E. Scheduling (clinics, services, demos)
- F. Recovery: abandoned cart and unpaid link
- G. Collections (overdue payments)
- H. Post-sale, onboarding and repurchase
- I. Reception and triage (one number, many departments)
- J. Industry notes

---

## A. Sales (SDR / consultative)

**Goal**: turn an interested lead into a concrete next step (trial, purchase link, demo, visit), in an order of preference the business chooses.

**Instructions**: GOAL (next steps in order of preference, and the closing rule: when the lead asks how to start, give the link and the one first step, ask nothing else) · STYLE (length, emoji, how to use the name) · OPENING (introduce once, open question about the lead's context; returning lead: no re-introduction, resume from the summary) · QUALIFICATION (the 3 or 4 things that decide the recommendation for this business, asked one per reply, skipped when already known) · RECOMMENDATION (rule that maps the lead's situation to one product or plan, and why) · VALUE (link each feature to the pain the lead told; at most 2 or 3 features) · OBJECTION "…" (one instruction per frequent objection, with the company's real answer) · HAND-OFF · TRUTH · OUT OF SCOPE · CONTACT (only on non-WhatsApp channels, see channels.md).

**Hand-off**: asks for a person, demo or meeting; wants a proposal or contract; enterprise or custom deal; negotiates a discount the agent cannot give; technical question it cannot answer.

**App options**: buttons on, hand-off on request on, "ready to buy" on if a person closes, follow-up on (2 attempts), payment link if the business sells by link, calendar if demos are booked.

**Bench focus**: price question in the first message, "é caro", "vou pensar", vague lead ("oi"), competitor comparison, lead ready to buy, discount request.

## B. Closer / e-commerce and catalog

**Goal**: answer product questions fast and close in the conversation (payment link, checkout link, store).

**Instructions**: GOAL (close in the chat; the purchase path) · CATALOG (use the price list and photos; when several products fit, offer at most 3 with the difference in one line each; ask size/color/quantity only when needed for the order) · ORDER (confirm items, quantity, total and delivery before sending the link) · SHIPPING AND DELIVERY (real rules: regions, deadlines, cost, pickup) · PAYMENT (methods, installments; send the link when the order is confirmed) · EXCHANGES AND RETURNS (policy) · OBJECTION "frete caro", "achei mais barato" · HAND-OFF · TRUTH (stock and delivery dates only from the facts).

**Hand-off**: custom order, wholesale, complaint, stock doubt, payment failure.

**App options**: product photos on, buttons on, payment link with a maximum amount, follow-up on.

**Bench focus**: "quanto custa X" with an alias name, product not in the catalog, order with quantities, shipping question to an uncovered region, "manda foto".

## C. Qualification and routing (BANT)

**Goal**: learn need, budget range, decision maker and timing in a natural conversation, then hand qualified leads to a seller with a complete summary and keep unqualified ones nurtured.

**Instructions**: GOAL (qualify and route; this agent does not close) · QUALIFICATION (the business's criteria for a qualified lead, concrete: e.g. "empresa com 5+ funcionários e prazo de até 3 meses") · HOW TO ASK (one item per reply, linked to what the lead just said; never a list) · ROUTING (qualified → transfer with summary; not a fit → say kindly what the company does not do and offer the alternative; too early → offer material and let follow-up resume) · SUMMARY (exact fields to put in the transfer summary) · TRUTH.

**Hand-off**: every qualified lead (this is the success event). Turn on "ready to buy".

**Bench focus**: lead that answers everything in one message (do not ask again), lead that refuses budget, non-fit lead, decision maker is someone else.

## D. Support / customer service (SAC)

**Goal**: solve the customer's issue with the knowledge base and policies, or open the path to a person with the case already explained. Success is a resolved issue, not a sale.

**Instructions**: GOAL (resolve; sales only when the customer asks) · IDENTIFY (what is needed to find the case: order number, email of the account, CPF only if the business really needs it and never full card data or passwords) · DIAGNOSE (ask the one question that splits the most common causes) · ANSWER FROM THE BASE (step by step in short messages; if the base does not cover it, say so) · POLICIES (refund, exchange, warranty, SLA, with the real numbers) · EMPATHY (acknowledge the problem in one sentence before solving; no defensive tone; apologize once, not every message) · ESCALATION · CLOSING (confirm it was solved; do not end with a sales pitch).

**Hand-off**: anger or a legal threat (Procon, lawyer), refund or charge dispute, bug the base does not explain, account access, personal data request (LGPD), the customer asks a second time for a person.

**App options**: media on (send manuals), hand-off on request on, follow-up off (a silent customer was usually helped), tone professional or friendly, verbosity balanced.

**Bench focus**: angry customer, question outside the base, refund request beyond policy, "quero falar com um humano", customer who sends a screenshot.

## E. Scheduling (clinics, services, demos)

**Goal**: book a confirmed slot in the calendar (or send the Calendly link) with the details the provider needs.

**Instructions**: GOAL (book) · SERVICES (what can be booked, duration, preparation, price or "a partir de", who it is for) · BOOKING (ask only what booking needs: service, preferred day and period; offer 2 or 3 options; confirm date, time, address or link) · RULES (hours, advance notice, cancellation and no-show policy, insurance/convenios) · CONFIRMATION (only the calendar's confirmation counts; never say "agendado" without it) · HAND-OFF.

**Hand-off**: urgent or clinical question (health: never diagnose or prescribe; for emergencies, tell them to call emergency services), rescheduling outside rules, insurance authorization.

**App options**: calendar connected, buttons on (periods as buttons), booking link if Calendly, follow-up on 1 attempt, tone friendly.

**Bench focus**: "tem horário amanhã?", lead gives a time outside business hours, rescheduling, health question that asks for a diagnosis, lead asks price before booking.

## F. Recovery: abandoned cart and unpaid link

The first message is sent by an automation (triggers "Carrinho abandonado" or "Link de pagamento não pago", with variables like {{link_carrinho}}, {{valor}}, {{produto}}, {{link_pagamento}}). The agent handles the replies.

**Goal**: find out what stopped the purchase and remove that obstacle; the success event is the payment.

**Instructions**: GOAL · CONTEXT (the lead was reminded about a cart or link; do not pretend it is a fresh conversation) · DIAGNOSE (one question: price, shipping, payment method, doubt about the product, just forgot) · SOLVE (resend the link, explain installments or Pix, answer the doubt; offer a coupon only if the business has one and its rule) · RESPECT (if they say they are not interested, thank them and stop; never insist twice) · HAND-OFF.

**App options**: payment link on, follow-up 1 attempt at most (the automation already reminded), buttons on.

**Bench focus**: "achei caro", "o pix não foi", "já comprei" (confirm and stop), "não quero mais".

## G. Collections (overdue payments)

**Goal**: get the payment or a payment commitment while keeping the customer relationship.

**Instructions**: GOAL · TONE (respectful, never threatening, no public exposure, no messages outside the business's hours; follow the consumer protection rules of the country, e.g. CDC art. 42 in Brazil) · IDENTIFY (confirm you are talking to the account holder before stating amounts) · OPTIONS (the real ones: second copy, Pix, installments, new due date, and who can approve a deal) · COMMITMENT (record the promised date in the transfer summary or note) · DISPUTE (if the customer disputes the charge, stop collecting and hand off) · TRUTH (no invented fees, interest or consequences).

**Hand-off**: dispute, negotiation beyond the allowed options, financial hardship, a third party answers.

**App options**: payment link or recurring billing, follow-up off (collections cadences are automations), tone professional.

## H. Post-sale, onboarding and repurchase

**Goal**: make the customer succeed with the purchase (activation, first use) and come back (repurchase, upsell, referral).

**Instructions**: GOAL · ONBOARDING STEPS (the 3 to 5 steps to first value, one per message, checking each one) · USAGE QUESTIONS (from the base) · REPURCHASE (when the cycle is due, a useful reminder; the automation "Hora de recomprar" sends the first message) · REFERRAL (offer the referral link only after a positive moment) · FEEDBACK (ask for a rating once) · HAND-OFF to support for problems.

**Bench focus**: customer stuck in step 2, "acabou o produto", complaint after delivery.

## I. Reception and triage (one number, many departments)

**Goal**: understand in one or two messages what the person needs and route: answer simple FAQs, hand sales leads to sales, support cases to support.

**Instructions**: GOAL · MENU-LESS TRIAGE (identify the intent from the message; if unclear, offer the 3 or 4 options as buttons) · QUICK ANSWERS (hours, address, links: the facts) · ROUTING (which intents go to which department and what to collect first) · HAND-OFF summary with the intent.

Note: routing to a department is done by the team's hand-off rotation (departments of the conversation). State the intent clearly in the transfer summary.

## J. Industry notes

- **Real estate**: qualify purpose (buy/rent), region, budget, bedrooms, financing; send listings from the base; schedule visits; never promise approval of financing.
- **Health and wellness**: never diagnose, prescribe or promise results; emergencies go to emergency services; respect privacy (no clinical details in group chats or summaries beyond the needed); regulated advertising (e.g. CFM/CFO in Brazil) forbids before/after promises.
- **Education and courses**: start date, format, workload, certificate, payment plans; objection "não tenho tempo"; trial class or enrollment link.
- **B2B / SaaS**: volume and integration questions decide the plan; price math for the lead's volume; demo or trial as next step; technical precision over enthusiasm.
- **Restaurants and delivery**: menu from the price list, delivery area, time, payment; order confirmation before closing.
- **Financial services and insurance**: no promises of returns or approval; mandatory disclaimers the business gives; hand off before any contract.
- **Auto**: model, year, trade-in, financing; schedule test drive.
- **Events and tourism**: dates, availability, group size; never confirm availability the facts do not show.
