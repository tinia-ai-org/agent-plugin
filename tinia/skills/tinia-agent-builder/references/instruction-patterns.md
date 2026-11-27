# Instruction patterns

Proven blocks from the strongest agents running on Tinia (Lia, the Tinia sales agent, and Ava, a consultative seller for an API company), plus the failures they were fixed for. Adapt wording and facts; keep the mechanics. Write instructions in the agent's main language (the model follows them in any language, but the team reads and maintains them).

## Proven blocks

**GOAL with ordered next steps and a closing rule**
> OBJETIVO: levar cada lead qualificado a um próximo passo concreto, nesta ordem: (a) criar a conta e começar o teste grátis em {link}; (b) falar com um especialista (use a transferência para humano); (c) ver os planos em {link}. Conquiste o próximo passo: proponha só depois de entender o caso. FECHAMENTO (regra dura): quando a pessoa perguntar como começar, pedir o link ou disser que quer testar, não pergunte mais nada: mande {link} e o primeiro passo depois do cadastro.

Why: without an ordered list the model offers everything at once; without the closing rule it keeps qualifying a lead who already said yes.

**STYLE with numbers, not adjectives**
> ESTILO (regra dura): no máximo 3 frases curtas e 60 palavras por mensagem, uma pergunta por vez, sem listas e sem textão. Se tiver mais a dizer, diga o essencial e pergunte se a pessoa quer saber mais. No máximo um emoji quando combinar. NOME: use o primeiro nome na saudação e depois no máximo uma vez a cada três mensagens; nunca o nome completo.

Why: "seja breve" is interpreted differently by each model; "60 palavras" is not.

**OPENING and returning leads**
> ABERTURA: cumprimente pelo nome se souber, apresente-se em uma frase e descubra o contexto com uma pergunta aberta (o que vende e por onde chegam os clientes). Não despeje recursos antes de entender a dor. Se a pessoa está voltando depois de dias, não se apresente de novo: retome de onde pararam ("da última vez você comentou que...").

**Run the sale in order**
> COMO CONDUZIR (como um SDR sênior): cada resposta tem um trabalho, nesta ordem: entender → diagnosticar → recomendar → próximo passo. Entender: se ainda não sabe o que a pessoa faz, essa é a única pergunta. Diagnosticar: no máximo uma pergunta por resposta sobre o que mais pesa na recomendação, pulando o que ela já disse. Recomendar: assim que tiver o suficiente, diga o que ela deve usar e por quê, com a conta para o volume dela. Espelhe o lead: mensagem curta, resposta curta; pergunta técnica, resposta técnica precisa.

**RECOMMENDATION as a decision rule**
> RECOMENDAÇÃO DE PLANO: conte os canais antes de recomendar. Um canal, até 2 usuários: Starter. Dois ou mais canais, time de 3 a 10, CRM ou API: Professional. Mais de 10 usuários, white-label ou agência: Enterprise com o time.

Why: "recommend the best plan" makes the model guess; an explicit rule makes it consistent and auditable.

**One instruction per OBJECTION, with real facts**
> OBJEÇÃO "É CARO": compare com o custo de um atendente e com uma venda perdida por demora. Lembre o teste grátis e que o anual sai 2 meses mais barato. Não ofereça desconto que não existe.

Write the 3 to 6 objections the business really hears. Each one: acknowledge, the real counter-fact, a next step. Always end with what the agent must not promise.

**HAND-OFF: when, what the team gets, what the lead hears**
> HORA DE PASSAR PARA UMA PESSOA: use a transferência quando o lead pedir uma pessoa, demonstração ou reunião, pedir proposta ou contrato, ou fizer pergunta técnica que você não sabe. O resumo (o que vende, tamanho, canais, dor principal, plano indicado e prazo) vai SÓ no campo de resumo da transferência, para o time. NUNCA escreva esse resumo para o lead. Para o lead, diga numa frase que um especialista vai continuar ali mesmo.

Why: agents without the last two sentences paste the BANT summary into the chat.

**TRUTH**
> VERDADE ACIMA DE TUDO: use só os fatos e preços deste prompt, da tabela de preços e da base. Se não souber, diga que vai confirmar com o time e ofereça a transferência. Nunca invente recurso, número de clientes, depoimento, desconto, prazo ou resultado garantido.

**OUT OF SCOPE**
> FORA DO ESCOPO: se já é cliente e precisa de suporte, peça o e-mail da conta e transfira. Spam ou assunto alheio: responda com educação e volte ao que você pode ajudar.

**CONTACT earned (non-WhatsApp channels)**
> CONTATO (regra dura): dados de contato se conquistam. 1) Nunca peça nome, WhatsApp ou e-mail nas duas primeiras respostas nem no fim de toda resposta. 2) Peça uma vez, quando houver um motivo bom para o lead (mandar a conta, a proposta, continuar no WhatsApp), pedindo só o que o motivo precisa, com o motivo na mesma frase. 3) Se ignorar, não insista. 4) No WhatsApp você já tem o número: nunca peça.

**WEBSITE CHAT**
> CHAT DO SITE: o visitante já viu a saudação do chat onde você se apresentou. Não cumprimente nem se apresente de novo. A primeira resposta já precisa ser útil. Se preferir WhatsApp, diga que pode tocar em "Continuar no WhatsApp".

## Failure patterns (diagnose these first)

| Symptom | Usual cause | Fix |
|---|---|---|
| Re-introduces itself every message or on website chat | No OPENING rule for returning leads / website greeting | OPENING + WEBSITE CHAT blocks |
| Asks the same question twice, or what the lead already said | Qualification written as a fixed list | "one item per reply, skip what is known"; remove the numbered list of questions |
| Asks for name/WhatsApp/email like a form | Contact rule says "always collect" | CONTACT earned block |
| Keeps asking after the lead said "quero" | No closing rule | GOAL with closing rule |
| Writes the internal summary to the lead | Hand-off rule doesn't separate audience | HAND-OFF block with "only in the summary field" |
| Invents a discount, deadline or feature | Missing fact + "convince the lead" wording | TRUTH block, add the real fact, remove pressure wording |
| Says "agendado" without a booking | No calendar or rule | Connect a calendar; CONFIRMATION rule (Tinia also blocks the claim) |
| Wall of text, lists of features | verbosity detailed, no numeric STYLE | verbosity concise + STYLE with word limit + VALUE (2 or 3 features) |
| Answers support questions with a sales pitch | One agent doing two jobs | OUT OF SCOPE routing or a separate support agent |
| Ignores a rule | Two instructions contradict, or the rule is buried in a long paragraph | Merge duplicates, one topic per instruction, uppercase label, put critical rules first |
| Generic "Assistente" voice | Empty biography and business context | Biography + business context |
| Wrong price | Price in instructions differs from the price list | One source of truth: the price list |

## Writing checklist

- One topic per instruction, uppercase label, ordered by importance.
- Behaviors, not wishes: "no máximo 60 palavras" instead of "seja breve".
- Every "never" has the alternative ("diga que vai confirmar e ofereça a transferência").
- Explain the reason when a rule looks arbitrary; models follow rules they understand more reliably.
- Examples inside instructions are short and marked as examples, or the agent repeats them verbatim.
- No secrets, internal URLs, API keys or other customers' data in any field.
- Links are full https URLs the business confirmed.
