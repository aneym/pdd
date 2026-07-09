# The grill protocol

A **grill** is a focused interview. The agent puts its open questions in front of
the project owner, all of them, each with a recommendation, and keeps
distilling the owner's answers until both sides share the same understanding of
what the project is for. It is how PDD turns a fuzzy idea into a purpose canon.

The word sounds adversarial, and in a sense it is: the agent pushes on soft
spots, surfaces the choices hiding inside a vague goal, and refuses to let an
important fork stay unresolved. But it is always in service of the owner. The
goal is a shared, honest picture, not a quiz.

This protocol is PDD's adaptation of the grill from how-to-work (htw). The
mechanics of running it live (posting cards, collecting answers, appending the
ledger) come from htw (see the README's install section). This file is the
*doctrine*: how a good PDD grill behaves.

## Plain language, always

Every question is written for the owner as a decision-maker, not as an engineer.

- **Short.** Two to four plain sentences per question. If it needs a paragraph,
  it is not distilled yet.
- **No jargon, no tool names, no acronyms**, unless the question is literally
  about that tool. The owner should never have to look up a word to answer.
- **Concrete scenarios, not shorthand.** Instead of "what's your consistency
  model," ask "if two people edit the same thing at once, whose change wins — or
  should that never be able to happen?" Paint the situation; let the owner react
  to something real.
- **Teach when needed.** If the owner does not understand a choice, explain it in
  approachable terms and give them enough to decide. One path for everyone —
  technical owners state their preference when they have one; everyone else gets
  a recommendation and a short explanation. Progress never stalls on a word.

## Ramble against everything, never a one-question gate

Do not march the owner through questions one at a time as if each were a locked
door. Put the open items in front of them and let them **talk against all of it
at once, in any order.** People think out loud; a good grill captures the whole
spill, not just the answer to the current question.

The agent's job is to listen to the ramble, pull the decisions out of it, and
distill each one into the ledger, then remove it from the open list. What is
still open stays visible (see the presentation law); what is answered disappears
from the surface and becomes a recorded decision.

Order still matters for *dependent* questions: when the answer to one changes
what you would ask next, resolve it first. But independent questions are shown
together, and the owner is never blocked from jumping ahead.

## Ask only genuine forks (the hygiene law)

The fastest way to ruin a grill is to ask questions that are not really
questions. Two tests keep the grill sharp:

- **The canonical-answer test.** When a best answer already exists (from
  security practice, from a spec, from the field's convergent pattern, from plain
  convention) it is **not** a grill question, no matter how weighty it feels.
  Asking it just launders a decision the agent should have made onto the owner.
  Decide it, record it as a derived decision, move on.
- **The two-owners test.** The only questions that earn a card are the ones where
  *two reasonable owners of this same project would answer differently.* Taste,
  preference, risk tolerance, and private context the agent cannot see. Those
  are real forks. Everything else, the agent settles itself.

Fewer, sharper questions beat a long list. A grill that asks twenty questions
when three were real forks has failed, even if every answer is captured.

## The derived-answer rule

Never ask the owner something their earlier statements already answer. If it can
be worked out from what they have said, from the codebase, or from an obvious
default, **work it out**, record it as a *derived* decision (noting it was
derived, not asked), and keep going. Re-asking settled ground is a tax on the
owner's attention.

## Technical parameters are never the owner's questions

Ports, library versions, file layouts, retry counts, framework config: these are
implementation details, not owner decisions. The agent picks them. They may be
recorded in the ledger for the record, but they never appear as a question on a
surface the owner reads. The owner decides *what the project is for and what it
should feel like*; the agent decides *how to build it.*

## Recommendations, not absolutes

Every open item carries a recommendation. Every recommendation is a **default or
a posture, not a ban.** PDD does not write "never" or "always" into a project's
canon except where a real, deterministic gate enforces a true invariant. The
owner can always override a posture; that is what makes it a posture.

## What the grill produces

- A **purpose canon** the owner and every future agent can read (see
  `PURPOSE.template.md`).
- A **decisions ledger**: each settled question distilled to one dated line
  (see `decisions-ledger.template.md`).
- **Unknowns recorded as unknowns.** It is fine to be unsure. An open question
  the owner cannot answer yet becomes a *figure-out-through-building* item in the
  canon, a real first-class entry, not a forced fake decision.
