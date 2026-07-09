# PDD: Purpose-Driven Development

**Start every project by deciding what it's for. Write that down where agents read it.
Let everything else be derived from it.**

PDD is a way of building software with AI agents where the project's *purpose*, not a task
list, is the source of truth. Before any building starts, an agent interviews the owner (a
[grill](reference/grill-protocol.md)) until they share an honest picture of what the project is
for. That picture becomes a small set of canonical files any agent can read in a minute. From
then on, agents make decisions from the purpose instead of asking the owner to re-decide things,
and the owner stays in the flow of just discussing features and building them out.

It works the same whether the owner is an engineer or has never written code. Technical owners
state preferences when they have them; everyone else gets recommendations in plain language.
When the owner doesn't understand a choice, the agent teaches. Progress never stalls on a word.

## The four canonical pieces

A project is bootstrapped when these four things are decided, written down, and easy to change:

1. **The purpose**: what the project is for, as a northstar plus a few *charters* (see below).
2. **The tools available**: what already exists in the environment: services, accounts, APIs,
   agent tools.
3. **The tools we're willing to have**: the acceptance boundary. What the owner will adopt,
   pay for, and depend on.
4. **The tech stack**: chosen once, recorded, and not re-argued every session.

All four are living canon: okay to change over time, never okay to be unwritten. Being unsure is
fine too. An open question becomes a *figure-out-through-building* item, recorded as such.

## The purpose tree

```
purpose          the northstar: one paragraph saying what this is for and what success is
  └─ charters    a few stable feature goals: WHY each major piece exists, what it serves
       └─ lanes / atoms   the actual work, each citing the charter it serves
```

- A lane that can't name its charter is either missing purpose or shouldn't exist.
- When the purpose is amended, what gets built next is re-ranked, so purpose stays upstream of
  the work instead of drifting behind it.
- For decomposing charters into independently improvable lanes and atoms, pair PDD with a
  readiness/decomposition skill (we use atomic-readiness-style loops; any seam-disciplined
  decomposition works).

## The two laws

Everything in this toolkit obeys two short laws. Read them before using anything else.

- **[The presentation law](reference/presentation-law.md).** Any surface shown to a person
  carries exactly two things: open items that need them (at the top, each with a
  recommendation) and the synthesis of where things landed. Never a replay of questions they
  already answered.
- **[The grill protocol](reference/grill-protocol.md).** Plain language, concrete scenarios,
  ramble-against-everything, ask only genuine forks, derive what's derivable, recommend always,
  no absolutes.

## Install

The skill is markdown files agents read. There is no build step. The skill references its
reference docs and templates by relative path, so install all three together:

```bash
# copy the skill + its reference docs and templates into a project
# (Claude Code convention shown; adapt for your harness)
git clone --depth 1 https://github.com/aneym/pdd /tmp/pdd
mkdir -p .claude/skills/pdd
cp /tmp/pdd/skills/pdd/SKILL.md .claude/skills/pdd/
cp -R /tmp/pdd/reference /tmp/pdd/templates .claude/skills/pdd/
rm -rf /tmp/pdd
```

Then, in a session: invoke `/pdd`. On a brand-new project it **guides**: runs the grill, writes
the canon, injects the CLAUDE.md block. On an existing project it **checks**: repairs mechanical
drift automatically and surfaces only true judgment calls.

For running ledgers and doc pipelines around the canon, PDD pairs with
[how-to-work](https://github.com/aneym/how-to-work) (`npx github:aneym/how-to-work`). Its
grill mechanics, append-only ledger, and doctor pattern are the proven machinery this standard
was extracted from.

## What's in this repo

```
skills/pdd/SKILL.md                  the core skill: guide or check a project's canon
templates/PURPOSE.template.md        the northstar + charters skeleton
templates/decisions-ledger.template.md
templates/claude-md-injection.md     the ≤10-line block a project's CLAUDE.md gets
reference/presentation-law.md        the law every user-facing surface obeys
reference/grill-protocol.md          how a good grill behaves
```

## Prior art, honestly

The *document* isn't the new part. AGENTS.md standardized the agent onboarding file; GitHub's
Spec Kit proved constitution-consulted-every-phase; northstar.md patterns exist several times
over; Ralph-style loops proved externalized state per atomic task. PDD adopts those shapes.
What PDD adds is the combination nobody packaged: the interview as the origination mechanism
(a grill to shared understanding, not a form to fill), a purpose tree instead of a linear spec
chain, and work derived from purpose rather than task decomposition. The presentation law keeps
the human's screen honest the whole way.

## Open (figure-out-through-building)

- **A visual walkthrough surface.** A bundled HTML page (open items on top, ramble box,
  synthesis below) so owners can read everything and talk against it. A prototype exists in a
  private project; generalizing it is next. *Recommendation: ship it as a template in v2.*
- **how-to-work on npm.** Today it installs via `npx github:`. *Recommendation: publish both
  packages to npm once the skill stabilizes.*
- **More case studies.** PDD's first full run produced a real product's canon in one session.
  *Recommendation: run it on two more projects before calling the standard 1.0.*

MIT. See [LICENSE](LICENSE).
