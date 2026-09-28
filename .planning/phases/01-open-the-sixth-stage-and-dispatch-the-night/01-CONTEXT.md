# Phase 1: Open the sixth stage and dispatch the night - Context

**Gathered:** 2026-09-28
**Status:** Ready for planning

<domain>
## Phase Boundary

This phase creates the sixth pipeline stage — a delivery build that the pipeline and the
repository's front door both declare, replacing the current five-stage claim — and makes it
possible for a day's agreed, signed work to be dispatched into that stage at the end of the
working day to run unattended overnight. It is the root of the whole delivery half: nothing that
writes into the sixth stage (Phases 2-5) can land before this phase creates the directory and the
dispatch path.

**Known gap — must close before planning finishes:** the roadmap's own text ("What the new stage
falsifies is already located...") implies `PIPELINE.md`, `README.md` (lines 6, 16, 27, 54), and
`prompts/documentation/HANDOFF.md` (line 192) already exist in the target repo with specific
"five stages" content this phase edits to "six." **None of these files exist yet in
`go-backend-starter`** (confirmed: repo currently holds only `.planning/`, `analysis/`, and a
generic top-level `README.md`). The user has confirmed this is the correct repository and will
supply/create these files themselves before planning finishes. Research and planning should
proceed on the assumption these files will exist with the structure described in the requirement
cards and roadmap, but this gap must be closed — the files supplied — before `gsd-plan-phase 1`
can produce an executable plan against real file contents rather than assumed ones.

</domain>

<decisions>
## Implementation Decisions

### Sixth-stage directory name (Decision 2 — required to close this phase)
- **D-01:** Keep the working name `prompts/delivery/` for the sixth-stage directory (do not
  rename to `prompts/execution/` or anything else). — **Reversibility:** one-way — a rename after
  Phase 2 begins writing round files into this directory requires renaming the directory plus all
  twenty-three occurrences of the string across `REQUIREMENTS.md` (twenty, across sixteen lines),
  `PROJECT.md` (two), and `STATE.md` (one); the cost rises with every round file Phase 2 onward
  adds, so treat this as locked now.
- **D-02:** Accept both consequences already baked into the `prompts/delivery/` working name,
  as-is: (a) round files run `D04` to `D06` rather than sorting into the day's actual run order,
  because `D01`-`D03` were minted first and renumbering would churn four other rows for nothing;
  (b) `D06` — a reporting-and-handover round — sits inside the delivery kit because the register
  proposes no separate reporting kit. — **Reversibility:** costly — renumbering later touches
  every reference to the affected round files across the package; moving `D06` out later requires
  standing up a new reporting kit and repointing every consumer of `D06`'s current location.

### Risk R-080 — the harness changing itself (Decision 5, due before this phase is planned)
- **D-03:** Mint `R-080` as a locked decision for this package's planning purposes, applying to
  **all eight phases**: every requirement in this engagement changes the harness that is shown to
  clients, and the harness is being used to change itself. Plans for this and every later phase
  should account for this risk being real and tracked, not treat it as absent. — **Reversibility:**
  reversible — this is a risk-tracking stance, not a code or contract change; it can be revised in
  a later round without breaking anything already built.
  - **Follow-up required outside this package (not satisfied by this decision alone):** the
    roadmap's own closure text for Decision 5 specifies a two-part act — *"the practitioner
    confirms the wording, it is appended to his notes under a new dated heading... and `R-080` is
    minted."* That dated heading belongs in the external `workshop-docs/` practitioner notes,
    which are **not part of this package** (published on the handover site only). This CONTEXT.md
    decision authorizes downstream agents to treat `R-080` as real and tracked; it does **not**
    itself complete the formal RAID-sheet mint, which still requires the user to append that
    dated heading to the external notes file directly.

### Dispatch trigger mechanism
- **D-04:** The overnight run is triggered by the practitioner manually running one dispatch
  round (a prompt/command inside `prompts/delivery/`) at the end of the working day, then leaving
  — not a scheduled/cron job with no manual step. — **Reversibility:** reversible — switching to a
  scheduled trigger later is an operational change, not a contract break, provided the round
  itself stays invocable on demand. — **Rationale:** Success Criterion 3 states this in the
  roadmap's own words ("the practitioner runs one dispatch round at the end of a working day and
  leaves"), and the requirement card's source evidence ("when we close the computers at 5 o'clock
  in the evening, we want things to happen") describes a deliberate end-of-day action, not a
  passive schedule. **Assumption made under autopilot** (user unavailable for live confirmation
  at the time this was decided) — flagged here for review rather than treated as silently locked.

### the agent's Discretion
- **Delivery stage's `HANDOFF.md` format** (Success Criterion 4 — "states what the stage is
  handed and what it declares as output"): left to the planner/executor to follow the same
  convention as sibling stage handoffs already established elsewhere in the pipeline (e.g.
  `prompts/documentation/HANDOFF.md`) — state what is handed to the stage (the signed
  requirements package, per `PLAN100-10`/`SITE100-10`) and what it declares as output, rather than
  prescribing exact prose here. **Assumption made under autopilot** — user unavailable for live
  confirmation; flagged for review rather than silently locked.

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Files this phase edits (currently MISSING — user to supply before planning finishes)
- `PIPELINE.md` (repo root) — line 3 states the five-stage claim this phase must flip to six.
  **Not present in this repo yet.**
- `README.md` (repo root) — lines 6, 16, 27, 54 state the five-stage claim. **The generic
  README.md currently in this repo is the GSD handover README, not this file — it does not carry
  this content.**
- `prompts/documentation/HANDOFF.md` — line 192 states the five-stage claim. **`prompts/` does not
  exist in this repo yet.**

### Requirement cards for this phase
- `analysis/requirement-detail/PLAN100-10.md` — "Execute the agreed requirements": carries the
  package from the signed handover site into the delivery build.
- `analysis/requirement-detail/NIGHT100-10.md` — "Dispatch at day's end": the end-of-day
  unattended dispatch this phase must make possible.

### Roadmap
- `.planning/ROADMAP.md#phase-1-open-the-sixth-stage-and-dispatch-the-night` — phase goal, success
  criteria, assumptions, and the "Decides" field for Decision 2.
- `.planning/ROADMAP.md#open-decisions` — full text of Decision 2 and Decision 5, including
  measured blast radius and reversal cost for each.

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- None — `go-backend-starter` currently holds no application code, only the GSD planning package
  (`.planning/`, `analysis/`) and a generic top-level `README.md`. There is nothing yet to reuse.

### Established Patterns
- None observed in this repo. The sibling repo pattern referenced in this package's canonical
  refs (`prompts/<stage>/HANDOFF.md` per stage) is the pattern to follow once the missing files
  are supplied, per the agent's Discretion decision above.

### Integration Points
- The sixth-stage directory (`prompts/delivery/`) is the integration point every later phase
  (2 through 5) writes into. Nothing in this phase depends on prior phases (`Depends on: Nothing
  (first phase)` per ROADMAP.md).

</code_context>

<specifics>
## Specific Ideas

No specific implementation ideas beyond what's captured in the Decisions above — open to standard
approaches for how the dispatch round and `HANDOFF.md` are structured, within the constraints
already decided.

</specifics>

<deferred>
## Deferred Ideas

None — discussion stayed within phase scope.

</deferred>

---

*Phase: 1-Open the sixth stage and dispatch the night*
*Context gathered: 2026-09-28*
