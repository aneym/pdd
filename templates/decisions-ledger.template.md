# Decisions ledger

<!--
  The append-only record of every decision made about this project's purpose and canon.
  This is the "past" surface — the person-facing grill surface stays clean by moving
  every settled question here.

  How to use it:
    • One line per decision. Distill it — the reasoning can be a clause, not a page.
    • Group under a dated heading (newest at the top).
    • Bold a short label, then the decision. Note when a decision was DERIVED
      (worked out from earlier answers) rather than asked directly.
    • Never rewrite history. A newer decision that reverses an older one is a NEW
      line, not an edit — the conflict between them is itself worth keeping.

  If you use the how-to-work engine, its ledger is JSON Lines with the shape
  {ts, event, actor, summary} and is appended with `htw ledger add` so the schema
  stays consistent. This Markdown file is the plain-text equivalent for projects
  that are not running that engine — same idea, human-readable.
-->

## <YYYY-MM-DD>

- **<Short label>** — <the decision, distilled to a line or two.>
- **<Short label>** (derived) — <a decision the agent worked out from earlier
  answers rather than asking; recorded so the reasoning is not lost.>
- **<Short label>** — <the decision.>

## <earlier YYYY-MM-DD>

- **<Short label>** — <the decision.>
