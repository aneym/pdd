# The presentation law

This is the one rule PDD never bends. It governs every surface a person looks at
while a project is being bootstrapped or checked — a chat, a page, a printed
summary. It exists to prevent one specific failure: making a person re-read
things they already settled, and hiding the two things they actually need to see.

## The law

A surface shown to a person carries exactly two things:

1. **Open items** — the questions or gaps that still need this person. They sit
   **at the top**, and **each one comes with a recommendation** (the answer the
   agent would pick, and why).
2. **The synthesis** — a plain summary of where everything has landed so far.

That is all. No replay of questions already answered. No transcript of the
back-and-forth. The moment an item is settled, it leaves the top of the surface
and becomes a line in the ledger — the record lives there, not on the screen.

## Why each part

- **Open items at the top.** The person opens the surface and immediately sees
  what is being asked of them, with no scrolling. Their attention is the scarce
  thing; the top of the page is reserved for it.
- **A recommendation on every open item.** A question with no recommended answer
  pushes the work back onto the person. PDD always brings a recommendation — the
  person accepts, tweaks, or overrules, which is faster than deciding from
  scratch. When no preference has been stated, the recommendation is what moves
  things forward.
- **Never replay answered questions.** Once something is decided, showing it
  again as a question invites re-litigation and buries the still-open items. The
  decision is recorded in the ledger; the surface moves on.
- **Synthesis, not history.** The person should be able to read, top to bottom,
  what the project now believes about itself — not reconstruct it from a
  conversation log.

## The mirror rule

Any question the agent asks in **chat** must also appear on the **surface** the
person is looking at. The chat and the page never drift apart. If the agent
raises a fork out loud, that same fork shows up as an open item on the page, so a
person who only reads the page never misses a decision, and a person who only
follows the chat sees the same queue.

## What this looks like in practice

While bootstrapping, the surface is a short stack:

```
OPEN — needs you
  • <question 1>   Recommendation: <the pick, and why>
  • <question 2>   Recommendation: <the pick, and why>

WHERE THINGS STAND
  <plain synthesis of the purpose, tools, stack so far>
```

As each open item is answered it drops off the top and the synthesis grows. When
the last open item is gone, the synthesis inherits the whole surface — that is
the finished canon.

## Relationship to the ledger

The ledger (`decisions-ledger.template.md`) is the opposite surface: it is the
full, dated, append-only record — every decision, who made it, one distilled
line each. The person-facing surface shows the *present* (open + synthesis); the
ledger holds the *past*. Nothing is lost by keeping the surface clean, because
everything settled is already in the ledger.
