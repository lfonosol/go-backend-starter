# harness-v1

## What This Is

harness-v1 builds the pod's own harness — the tooling and process the team uses to run
AI-delivery engagements. Today that harness is a five-stage pipeline that ends at a published,
password-gated handover site. This engagement extends it into a delivery loop: work is dispatched
at the end of the working day, runs unattended overnight, and the morning opens on a ranked review
of every decision the run inferred. It also organises the handover site's content, generates the
artifacts that are currently assembled by hand, and closes the return path from a post-signature
review meeting back into the requirements.

The readers are the delivery pod itself and the receiving development team that picks this package
up and builds from it.

## Core Value

The harness runs a day's delivery without anyone present to press buttons, and the human's whole
job in the morning is reading a ranked list of decisions that each carry a reason and a reversal.

## Requirements

### Validated

(None yet — ship to validate)

### Active

The scope is the change register's 27 rows, `CR-010` to `CR-270`. Twenty-four are each mapped to
one delivery identifier and are grouped below; the three subtractions `CR-250`, `CR-260` and
`CR-270` are in scope and await a phase. Grouped here by the outcome each cluster delivers, and named by
the delivery identifier; the full statements, their sources and the change record behind each one
are in `REQUIREMENTS.md`, and the source quotation is attached to its phase in `ROADMAP.md`.

- [ ] The pipeline gains a sixth stage, and work is dispatched at the end of the day — PLAN100-10, NIGHT100-10
- [ ] An unattended run is entered by a round, runs as a verification loop, stops on a broken gate, and states its own boundary — NIGHT100-20, NIGHT100-30, NIGHT100-40, NIGHT100-50
- [ ] The run is closed by a round, and the day opens on a criticality-ranked review of inferred decisions, with lessons and problems recorded — MORNING100-10, MORNING100-20, MORNING100-30, MORNING100-40, MORNING100-50, MORNING100-60
- [ ] The daily session produces one pack: a demonstration, a proposal for what comes next, and a UAT handover a business tester can act on — DEMO100-10, DEMO100-20, DEMO100-30, DEMO100-40
- [ ] Every content area of the handover site carries an explicit organisation and a progressive-reveal or human-facing marking, and the reveal ships — SITE100-20, SITE100-40, SITE100-30
- [ ] The scope tracker and the weekly status report are generated rather than hand-assembled — SITE100-10, REPORT100-10
- [ ] Transcription feeds the planning tool during a session, post-signature review feedback re-enters the registers, and the signature apparatus leaves the kit — CAPTURE100-10, KIT100-10, KIT100-20

### Out of Scope

Two kinds of exclusion, and they are excluded for different reasons.

**Struck by the practitioner's own scope test, 2026-09-20.** The test was *does this cause a file
in this repository to change, be deleted, or be created?* It cut the register from 78 rows to 24.
The items below are recorded `In` on the scope-decision record and carry no register row: they
are ways of working the pod adopts rather than harness build work.

- LLM-first design — every capability behind an API and an MCP layer — a design principle applied inside each phase, not a phase
- Daily vertical slices, one or more features delivered and testable per day — the delivery rhythm the harness runs at
- Repository structure and a per-area agent as the control on reviewer effort — existing practice, already in the tree
- Architecture quality checks layered on the structure — depends on a technique owned by an external party; no adoption decision taken
- Accuracy measured against a golden data set agreed before the pipeline runs — no register row; a measurement practice
- Phases and steps constrained to isolated parts of the architecture — a direction given to the planning tool
- A roadmap step classifying each item as an application or an MCP command — proposed, no row
- Self-diagnosis: the agent reports what it did and why at the end of a task — proposed, no row
- Chat bots tied to the agentic work — proposed, no row
- Role-based views beyond the client view — stated as the eventual destination; the near-term scope is the client view plus progressive reveal

**Ruled out at the source.** Recorded `Out` on the scope-decision record.

- The next client engagement's own project scope — assigned to client preparation by the reading rule, not to harness requirements
- Client engagement logistics — travel, rooms, system access, account provisioning, creating the shared chat channel; no harness capability is stated for any of it
- The prior engagement's retrospective outcomes and maintenance handover — closed before the session; the source of the lessons, not work performed here
- The prior engagement's domain content — used in the session only as worked examples
- An external party's measurement technique — a candidate to evaluate, not something this engagement builds

## Context

**The requirements record is complete and signed off on its own terms.** The working lane holds a
normalised source index, a glossary, a scope-decision record, a decomposition, the change register,
the RAID register, and a provenance note per sheet. Two sources feed it, both tiered Authoritative:
a 93-minute working session transcript of 17 September 2026 (S-01) and the practitioner's own
dictated notes of 19 September 2026 (S-02). Every register row cites a source and a locus.

**The handover carries its own evidence, so a citation can be followed rather than believed.** The
raw sources are published on the site as `workshop-docs/` and are not in the downloadable archive; **the register sheets and provenance notes do not travel at
all**, because they are working files on the way to a Google Sheet that becomes the source of truth,
and what each of them holds about a requirement travels on that requirement's card instead.
`ROADMAP.md` attaches the evidence per
phase — the source quotation and its locus, the reasoning from each row's note, the judgment calls
the provenance notes record, the RAID rows that bite there, and the glossary terms in play — so an
agent starting a phase holds the sentence someone actually said instead of re-opening a settled
question.

**One reading rule governs every round.** At 01:26:28 of S-01 the speaker draws a boundary between
harness content and client preparation. That boundary marks emphasis, not a cut — the whole
transcript is read for harness content. Two harness proposals sit after it, and a round that stopped
there would drop both.

**Two identifier namespaces, with a mapping between them.** The change register owns `CR-010` to
`CR-270` — the business's namespace, what was agreed, in the language of the approval, and it does
not move. The roadmap, the requirements and the requirement cards own family identifiers, the
delivery namespace the handover site renders and groups by. **Between them is a mapping, not an
equivalence:** one change record may become two delivery items, or two collapse into one. For
harness-v1 it is one-to-one across 24 of the register's 27 rows — `CR-250`, `CR-260` and `CR-270`
are subtractions and take a delivery identifier only when a phase adopts them — and it is written
in both directions, in the register's `Delivery ID` column and `REQUIREMENTS.md`'s change-record
column.

**Both namespaces are mint-once from here.** Rounds 8 to 11 renumbered the register flat because
nothing downstream cited the identifiers yet; the delivery namespace now cites every one of them, so
neither side is renumbered again. A retired row is retired in place.

**The engagement's subject is this repository.** harness-v1's requirements are largely changes to
this repository's own generator, prompt kits and workflow. One consequence a later reader should not
rediscover: a harness change reaching the template's default branch reaches every other engagement's
live site too. The practitioner took that deliberately — *"I want it to flow out to every client.
Nothing needs to freeze."* The brake exists and is not being used: a `.handover-freeze` file on an
engagement branch holds that one branch, and `.handover-freeze-all` on the default branch holds them
all.

**Where this engagement stops.** It produces the roadmap and as much phase planning as can be done
without building. Execution belongs to the receiving development team, in a repository this harness
is not running inside.

## Constraints

- **Handover**: the receiving team places this planning directory and runs `/gsd-plan-phase 1`, or the router command that detects state — **not** `/gsd-new-milestone`, which does not consume an existing roadmap and would regenerate and discard everything here
- **Identifiers**: two namespaces with a mapping between them — the change register keeps `CR-010` to `CR-270` and does not move; the roadmap, requirements and cards use family identifiers in the grammar `board/config.mjs` owns. Both are mint-once, gapped by ten, retired in place, never renumbered. The mapping is written in both files so either one leads to the other
- **Engineering discipline**: no runtime dependency beyond `@vercel/functions`; no framework; no bundler; fail-closed builds that name the file, line and construct; one source for anything shared; seam modules with no top-level I/O
- **Tech stack**: Node 24.x, ES modules, `node:test`, ESLint 10 flat config, Vercel with `framework: null` and edge-runtime routing middleware
- **Writing rule**: every path the snapshot exports describes an engagement by shape, never by name
- **The working lane is read-only to this stage**: anything a planning round would want to add to the engagement repository's `workbook/` is raised with the practitioner instead
- **Sequencing**: KIT100-20 (Drop the signature record) is scheduled for the hardening stage on the practitioner's own instruction

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| Scope is the register's 24 rows, not the 24 `In` rows of the scope-decision record | The practitioner ran an explicit scope test on 2026-09-20 — does this cause a file here to change, be deleted or be created? — and it cut 78 rows to 24. The struck items are ways of working, not build work | — Pending |
| Phases are ordered by dependency, each delivering a visible outcome | The practitioner's call, 2026-09-20. The sixth-stage directory must exist before five rules can write clauses into files inside it; the site work depends on nothing and follows | — Pending |
| Two identifier namespaces, mapped rather than equated | **Corrects an earlier decision that the register's `CR-` numbers were carried verbatim into delivery.** Renumbering the register was refused — it is the business's approval view and traceability depends on its string. But the handover site's identifier grammar is family code, group number, hyphen, item number, and a flat `CR-010` satisfies none of the five rules that enforce it; that was measured against the parser with a conforming control in the same run. So the register keeps its namespace, delivery gets its own, and the mapping is written in both directions in one pass | — Pending |
| ROADMAP.md carries the evidence behind it, per phase | Reversed in the same sitting on 2026-09-20. It was first written in the standard shape with the enrichment held as a later stage; the practitioner then asked for the derivation's evidence to travel with the roadmap, so an agent starting a phase holds the sentence someone actually said. **One condition rides with it and is the important half: evidence always, because the sources are always present; file mapping only where the code is available.** Where a codebase is not in hand there is no file column at all | — Pending |
| The handover carries its own evidence, and the site and the zip must agree | 2026-09-20. The published package carries the sources and the sheets behind its requirements. It resolves a straight inconsistency — the site renders the raw workshop documents under "The sources" and the downloadable package did not include them. **Blast radius, taken deliberately:** a raw working-session transcript is the most sensitive artifact an engagement holds; here it is the pod's own recording, and on a client engagement whether it travels is a per-engagement decision rather than a default | — Pending |
| `prompts/delivery/` is a working name, not the practitioner's decision | Adopted so the sixth stage is one kit and not two, over `prompts/execution/`. **The claim that it is "recorded in one place so it can be changed in one place" is not true of this package**, and the correction is Decision 2 in `ROADMAP.md`'s open-decisions appendix: that row is the single decision record, and the name is spelled twenty times across sixteen lines of `REQUIREMENTS.md`, twice here and once in `STATE.md` as consumers of it. It is decided in Phase 1, which creates the directory | ⚠️ Revisit |
| The self-modification risk is live, uncited, and not on the RAID sheet | Every requirement changes the harness that is shown to clients, and the harness is being used to change itself. The RAID round judged it a real risk and did not mint it, because it is in neither source and an uncited row would break the sheet's own guarantee. It is minted as `R-080` at the first round after the concern appears in a source; its only home in this package is Decision 5 in `ROADMAP.md` | ⚠️ Revisit |
| No general "all generation is interactive" rule; each generating row states its own mechanism | The practitioner struck the general rule mid-round: *"if it's a universal thing, then there'd be confusion at which one it applies to."* The cost is repetition on four rows | — Pending |

## Evolution

This document evolves at phase transitions and milestone boundaries.

**After each phase transition** (via `/gsd-transition`):
1. Requirements invalidated? → Move to Out of Scope with reason
2. Requirements validated? → Move to Validated with phase reference
3. New requirements emerged? → Add to Active
4. Decisions to log? → Add to Key Decisions
5. "What This Is" still accurate? → Update if drifted

**After each milestone** (via `/gsd-complete-milestone`):
1. Full review of all sections
2. Core Value check — still the right priority?
3. Audit Out of Scope — reasons still valid?
4. Update Context with current state

---
*Last updated: 2026-09-20 after initialization*
