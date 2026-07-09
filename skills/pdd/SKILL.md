---
name: pdd
description: Take a project from zero to one by co-authoring its purpose canon with the owner through a grill, then wiring that canon into every agent session. Dual-mode — GUIDE a brand-new project through inception, or CHECK an existing project's canon for gaps and drift. Use when starting a new project, when a project has no shared northstar, when asked "what is this project actually for", or when an existing purpose doc has gone stale.
when_to_use: Also use when onboarding agents to a project keeps requiring the same re-explanation, when work is drifting from what the project is for, or when a "set up the purpose / bootstrap this project" directive lands. Works for a completely non-technical owner as well as an expert.
version: 0.1.0
metadata:
  tags: [purpose, bootstrap, grill, canon, northstar, agents, doctor]
---

# /pdd

Fill in a project's shared understanding so it guides every agent, end to end.
The deliverable is a **purpose canon** — a short set of living, source-of-truth
files — and the wiring that makes every future agent session start from it. This
is the core skill of Purpose-Driven Development (PDD).

One path for everyone. A non-technical owner and an expert go through the same
flow. Experts state preferences when they have them; everyone gets a
recommendation on every open question. The invariant is approachable language,
and teaching the owner whatever they need so progress never stalls on a word.

## Mode selection

- **No purpose canon yet** (no `PURPOSE.md` or equivalent) → **GUIDE**. Walk the
  owner through inception and produce the canon.
- **Canon already exists** → **CHECK**. Audit it for gaps and drift, fix the
  mechanical problems automatically, and surface only the judgment calls.

## The four canonical pieces

Every project's canon is drilled through these four. They become source of truth —
fine to change over time, but always canon:

1. **The purpose** — the northstar plus its charters (what each major feature is
   for and why). This is the heart; the rest support it.
2. **The tools available** — what already exists in the environment: services,
   accounts, APIs, integrations the project can call on today.
3. **The tools we're willing to have** — the acceptance boundary. What the owner
   will adopt, pay for, or depend on going forward — and what they won't.
4. **The tech stack** — chosen and recorded once, so it is not re-litigated every
   session.

## The rules of every grill (apply in both modes)

Read `reference/grill-protocol.md` and `reference/presentation-law.md` once before
you start. The load-bearing rules:

- **Visual surface first.** Put the open questions in front of the owner — at the
  top of the project's one surface page (see "The one surface" below) — each with
  your recommendation. Let them **ramble against all of it at once, in any
  order.** Do not gate them through one question at a time.
- **Every open item carries a recommendation.** When the owner has stated no
  preference, the recommendation is what moves things forward. Accept, tweak, or
  overrule — all faster than deciding from nothing.
- **Answered items leave the surface.** The instant a question is settled, distill
  it to one line in the decisions ledger and **remove it from view.** Never replay
  answered questions. The surface shows only what is still open plus a synthesis
  of where things stand.
- **Mirror rule.** Any question you ask in chat must also appear on the surface the
  owner is looking at. The two never drift apart.
- **Derive, don't ask.** If the owner's earlier words, the codebase, or an obvious
  default already answer a question, work it out and record it as a *derived*
  decision. Re-asking settled ground is a tax on their attention.
- **Only genuine forks earn a question.** The test: *would two reasonable owners of
  this project answer differently?* If a best answer already exists (convention,
  security practice, a spec, the field's pattern), decide it yourself. Technical
  parameters — ports, versions, layouts — are never the owner's questions.
- **No absolutes.** Recommendations and canon are written as defaults and
  postures, not "never"/"always" bans — except where a real, deterministic gate
  enforces a true invariant.
- **Teach when needed.** If the owner does not understand a choice, explain it in
  plain terms and give them enough to decide. Progress continues.
- **Unknowns are first-class.** It is fine to be unsure. Record an unanswerable
  question as a *figure-out-through-building* item in the canon — a real entry,
  not a forced fake decision.

## The one surface

The owner looks at exactly **one page** for the whole purpose system: a single
HTML file, `docs/purpose/index.html` by default (adapt the path to the project's
docs convention and record it in the ledger). It is the rendered form of the
presentation law:

1. **Open — needs you** at the top: one card per open item, question in plain
   words, recommendation attached. Empty when nothing needs the owner.
2. **Where things stand**: the synthesis of the canon, readable top to bottom.
3. **A ramble box**: a text area with a copy button. The owner answers by typing
   thoughts in any order, copying, and pasting the dump into any agent chat.

Start it from `templates/surface.template.html`. Agents **regenerate** this page
on every GUIDE or CHECK pass — it is a view over the canon files, not a place
where content lives. The moment it accumulates status reports, project history,
or anything belonging to a different effort, it has drifted; rebuild it from the
canon. The mirror rule binds to this page: a fork raised in chat appears here,
and an item answered in chat leaves here.

## GUIDE — bootstrap a new project

Copy this checklist and check items off as you go:

- [ ] G1: Understand the project in one exchange — what is being made, for whom,
      and what "working" would look like. Lead the owner toward a purpose that
      *expands* ambition rather than scoping it down.
- [ ] G2: Grill the purpose. Open the four canonical pieces as questions on the
      surface (top, each with a recommendation). Let the owner ramble; distill
      each settled point to the ledger and drop it from view. Derive what you can.
- [ ] G3: Draw out the **charters** — the few, stable goals of the major features,
      each stating what it is for and why (which part of the purpose it serves).
      Keep them few and durable.
- [ ] G4: Record **unknowns** as figure-out-through-building items rather than
      forcing decisions.
- [ ] G5: Write the outputs from the templates:
        - `PURPOSE.md` ← `templates/PURPOSE.template.md`
        - a decisions ledger ← `templates/decisions-ledger.template.md`
        - the surface page ← `templates/surface.template.html`
        - inject the block from `templates/claude-md-injection.md` into the
          project's `CLAUDE.md` (or `AGENTS.md`), filling in the two paths.
- [ ] G6: Confirm the loop closes: open a fresh agent context, have it read
      `PURPOSE.md` via the injected pointer, and check it can state the purpose and
      name the charters. If it can't, the canon is not clear enough — sharpen it.

Done = the four outputs exist, they are plain-language and absolute-free, and a
cold agent session can state what the project is for from them alone.

## CHECK — audit an existing project (doctor pattern)

CHECK behaves like a doctor: it fixes mechanical drift on its own and only
interrupts the owner for genuine judgment calls.

- [ ] C1: Locate the canon (`PURPOSE.md`, the ledger, the CLAUDE.md injection,
      the surface page). Missing entirely? Recommend switching to GUIDE.
- [ ] C2: **Fix mechanical drift automatically** — stale paths in the injection,
      a CLAUDE.md missing the block, charters with no "serves" line, ledger
      entries that never made it into the doc, absolutes that crept in, formatting
      the templates define, a surface page that has drifted into a status collage
      or replays answered questions (regenerate it from the canon). Repair these
      without asking; report what you changed.
- [ ] C3: **Surface only judgment calls** — a charter that no longer matches what
      the project does, a purpose statement contradicted by recent work, two
      decisions in the ledger that conflict, a canonical piece never filled in.
      Present each as an open item with a recommendation, on the surface, per the
      presentation law. Do not silently "fix" a judgment call.
- [ ] C4: Report an exit status:
        - **0** — canon is healthy; nothing needed the owner.
        - **1** — mechanical drift found and fixed automatically; no judgment
          calls. Safe to accept the fixes and move on.
        - **2** — judgment calls surfaced; the owner needs to resolve the open
          items before the canon is trustworthy again.

Use the exit status so CHECK can run unattended in a loop: 0 and 1 need no human;
2 stops for the owner.

## Handoff — from purpose to work

/pdd produces the *why* (purpose + charters). It does **not**
decompose the project into buildable work — that is the atomic-readiness skill's
job. Once the canon exists:

- Hand the charters to an **atomic-readiness**-style decomposition skill to break
  each into independently-improvable lanes and atoms (seam-disjoint: parallel
  lanes never share files, so one person can run many lanes without conflicts).
- Enforce the citation rule: **every lane cites the charter it serves.** A lane
  that serves no charter is a signal to check the purpose, not to invent one.
- When the purpose is amended, re-weigh the work queue — atoms serving a
  downgraded charter drop in priority; a new charter can raise new work.

The full mechanics of running a grill live (posting cards, collecting answers,
appending a schema-checked ledger) come from the how-to-work engine — see the
README's install section for the dependency.
