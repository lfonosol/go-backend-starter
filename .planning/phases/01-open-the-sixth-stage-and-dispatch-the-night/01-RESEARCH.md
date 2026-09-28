# Phase 1: Open the sixth stage and dispatch the night - Research

**Researched:** 2026-09-28
**Domain:** Prompt-kit / documentation-pipeline scaffolding (no application code, no libraries, no runtime framework)
**Confidence:** MEDIUM — high confidence on what the in-repo planning package itself states (verified by direct read this session); low/assumed confidence on anything about the eventual unattended-execution substrate, because no source in this package specifies it and the three files this phase edits do not yet exist.

<user_constraints>
## User Constraints (from CONTEXT.md)

### Locked Decisions

**Sixth-stage directory name (Decision 2 — required to close this phase)**
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

> **Research correction to D-02's own phrasing — see `## Finding: D-02's "D04 to D06" describes
> the whole delivery kit, not this phase's output` below.** Read literally, D-02 could be
> misread as "Phase 1 creates round files D04 through D06." Per direct, verified evidence in
> `REQUIREMENTS.md`, Phase 1 creates only `D01-dispatch.md`. D-02's decision itself is not
> wrong — it correctly accepts the *numbering scheme* (which does run D01 through D06 across
> the whole delivery kit, out of day-order) — but it is not a instruction to scaffold four files
> that don't belong to this phase. The planner must not create `D02`, `D03`, `D04`, `D05`, or
> `D06` files in Phase 1.

**Risk R-080 — the harness changing itself (Decision 5, due before this phase is planned)**
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

**Dispatch trigger mechanism**
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

### Deferred Ideas (OUT OF SCOPE)
None — discussion stayed within phase scope.
</user_constraints>

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| PLAN100-10 | Execute the agreed requirements — the signed requirements package is carried past the handover site into the delivery build; creates the sixth-stage directory and edits `PIPELINE.md`/`README.md` | See `## Finding: what PLAN100-10 concretely creates`, `## Five-Stage → Six-Stage Edit Sites`, and `## Code Examples` |
| NIGHT100-10 | Dispatch at day's end — work is dispatched at the end of the working day and runs unattended overnight; creates `prompts/delivery/D01-dispatch.md` and `prompts/delivery/HANDOFF.md` | See `## Finding: what NIGHT100-10 concretely creates`, `## What "dispatch at day's end" concretely requires`, and `## Code Examples` |
</phase_requirements>

## Summary

This phase has no framework, library, or application-code dimension — it is pure repository
scaffolding for a markdown-based "prompt kit" pipeline. The concrete work is: (1) create the
`prompts/delivery/` directory containing exactly one round file, `D01-dispatch.md`, plus its own
`HANDOFF.md`; and (2) edit three existing files — `PIPELINE.md`, `README.md`, and
`prompts/documentation/HANDOFF.md` — so they declare six pipeline stages instead of five. All
three of those edit targets are **confirmed absent from this repository** as of this research
session; the user has been told this and must supply them before an executable plan can cite real
line contents.

The most consequential finding of this research is a **correction to CONTEXT.md's own Decision
2 (D-02) phrasing**: read literally, D-02 could lead a planner to scaffold four round files
(`D02` through `D06`, or `D04` through `D06`) inside `prompts/delivery/` during this phase. Direct,
line-cited evidence in `.planning/REQUIREMENTS.md` shows this is wrong — Phase 1's two
requirements (`PLAN100-10`, `NIGHT100-10`) create only `D01-dispatch.md` and `HANDOFF.md`. The
other five round files (`D02`, `D03`, `D04`, `D05`, `D06`) belong to Phases 2 through 5 and must
not be created here.

The second load-bearing finding concerns the dispatch mechanism itself: the requirement's own
source evidence ("when we close the computers at 5 o'clock in the evening, we want things to
happen") implies the practitioner's own machine goes offline at dispatch time, which means the
overnight run cannot be a foreground process on that machine. Nothing in this package's four
planning files states what execution substrate the overnight run actually uses — that is a real
open item this research surfaces rather than resolves.

**Primary recommendation:** Scaffold exactly `prompts/delivery/{D01-dispatch.md,HANDOFF.md}` plus
the directory; edit `PIPELINE.md`, `README.md`, and `prompts/documentation/HANDOFF.md`'s five-stage
claims to six once the user supplies those files; keep `D01-dispatch.md`'s Phase-1 content scoped
to *what the stage is handed and that it dispatches* — leave the verification-loop, stop-on-gate,
and automation-boundary clauses for Phase 2 to add into the same file (per `NIGHT100-30`,
`NIGHT100-40`, `NIGHT100-50`); and raise the execution-substrate question with the user as a
`checkpoint:human-verify` before or during planning, since no source in this package answers it.

## Architectural Responsibility Map

This phase has no browser/API/database tiers. The table below is adapted to the prompt-kit
domain's own tiers, as established by the repo's own (not-yet-created) conventions.

| Capability | Primary Tier | Secondary Tier | Rationale |
|------------|-------------|----------------|-----------|
| Six-stage pipeline declaration | Repository manifest (`PIPELINE.md`) | Front-door README (`README.md`) | `PIPELINE.md` is the pipeline's own source-of-truth stage list `[CITED: .planning/ROADMAP.md:203-204]`; `README.md` mirrors it in four more places for a human reader `[CITED: .planning/ROADMAP.md:203-204]` |
| Sixth-stage scaffolding (directory + `HANDOFF.md` + `D01-dispatch.md`) | New prompt-kit stage directory (`prompts/delivery/`) | — | This phase is what creates this tier; every later phase (2–5) writes into it `[VERIFIED: .planning/REQUIREMENTS.md:199-201, quoted below]` |
| Stage handoff contract ("what the stage is handed / declares as output") | Stage-local `HANDOFF.md` | Sibling `HANDOFF.md` convention (`prompts/documentation/HANDOFF.md`, `prompts/gsd-planning/HANDOFF.md`) | Each existing kit in this package has its own `HANDOFF.md`; the delivery kit follows the same per-stage-not-per-pipeline placement `[VERIFIED: .planning/REQUIREMENTS.md:142,144,165,238,246, quoted below]` |
| Dispatch trigger (manual round invocation) | Practitioner-invoked round file (`prompts/delivery/D01-dispatch.md`) | Execution substrate (unresolved — see Open Questions) | The round file is the entry point the practitioner runs by hand `[CITED: 01-CONTEXT.md D-04]`; where the process then keeps running after they leave is not stated anywhere in this package |
| Unattended overnight continuation (surviving the practitioner's machine going offline) | Execution substrate — **not named in any source** | — | `[ASSUMED]` — flagged as the phase's single largest technical unknown; see `## What "dispatch at day's end" concretely requires` |

## Package Legitimacy Audit

**Not applicable.** This phase installs no external packages, npm/pip/cargo dependencies, or
libraries of any kind. It creates and edits Markdown files only (`.md`) plus a directory. The
Package Legitimacy Gate protocol is skipped in full.

## Standard Stack

**Not applicable in the conventional sense.** There is no framework, runtime, or library choice
to make. The only "stack" is the repo's own existing convention for prompt-kit stages, which this
research documents below as the pattern to replicate (not a third-party dependency to install).

### Existing sibling-kit convention (verified this session)

| Kit directory | Round-file naming | HANDOFF.md present | Source |
|---|---|---|---|
| `prompts/workshop-prep/` | first round + standing handoff (unnamed round file) | yes (implied — "standing handoff") | `[VERIFIED: .planning/REQUIREMENTS.md:70-72]` — *"Creates the first round file and standing handoff under `prompts/workshop-prep/`."* |
| `prompts/documentation/` | `P-GEN-05-validate.md`, `P-GEN-06-apply-changes.md`, `P-GEN-07-scope-tracker.md`, `P-GEN-08-scope-tracker-validate.md`, `P-GEN-09-scope-tracker-merge.md`, `P-GEN-11-review-feedback.md` | yes, `prompts/documentation/HANDOFF.md` | `[VERIFIED: .planning/REQUIREMENTS.md:78,109,142-144]` |
| `prompts/gsd-planning/` | `P00-intake.md` | yes, `prompts/gsd-planning/HANDOFF.md` | `[VERIFIED: .planning/REQUIREMENTS.md:144]` — *"`prompts/gsd-planning/HANDOFF.md`, `prompts/gsd-planning/P00-intake.md`"* |
| `prompts/delivery/` (this phase) | `D01`–`D06` (this phase creates only `D01-dispatch.md`) | yes, `prompts/delivery/HANDOFF.md` (this phase creates it) | `[VERIFIED: .planning/REQUIREMENTS.md:164-165]` |

None of these sibling directories (`prompts/workshop-prep/`, `prompts/documentation/`,
`prompts/gsd-planning/`) exist in this repo yet either — confirmed via the same absence check
below. They are referenced only as the *naming convention* this package's own text describes,
carried over from whatever template/prior engagement this harness pattern originates from. There
is nothing to `npm view` or `pip index versions` here.

**Installation:** none required.

## Architecture Patterns

### System flow this phase enables (once complete)

```
Signed requirements package (handover site, out of this repo's scope)
        │
        │  PLAN100-10: "no hand step in between"
        ▼
prompts/delivery/HANDOFF.md   ── declares: input = signed package, output = dispatched build
        │
        ▼
prompts/delivery/D01-dispatch.md   ◄── practitioner runs this by hand, at end of working day
        │
        │  NIGHT100-10: dispatch happens here
        ▼
[ Phase-2 concern, not this phase's:
  verification-loop bound (NIGHT100-30), stop-on-broken-gate (NIGHT100-40),
  automation boundary (NIGHT100-50) — all three ADD CLAUSES INTO THIS SAME
  D01-dispatch.md file later; Phase 1 only needs the dispatch entry point
  and the "what it's handed" contract to exist. ]
        │
        ▼
Unattended overnight execution  ── substrate NOT specified by any source (see Open Questions)
        │
        ▼
Morning review (Phase 3, out of this phase's scope)
```

### Recommended file layout for this phase's output

```
prompts/
└── delivery/                     # sixth-stage kit — LOCKED name, do not rename (D-01)
    ├── HANDOFF.md                # what the stage is handed / what it declares as output
    └── D01-dispatch.md           # the one round file this phase creates
    # D02, D03, D04, D05, D06 do NOT belong to this phase — see Common Pitfalls #1
```

### Pattern: stage-local `HANDOFF.md` contract

**What:** every existing kit directory in this package's own text has its own `HANDOFF.md`
stating what the stage receives and what it declares as output, rather than one pipeline-wide
handoff document.
**When to use:** for `prompts/delivery/`, per CONTEXT.md's Discretion note.
**Evidence for the section names such a file conventionally carries:**
`[VERIFIED: .planning/REQUIREMENTS.md:245-246]` — *"`prompts/delivery/HANDOFF.md` section
Declared outputs."* — confirms at least one section is literally named **Declared outputs**.
`[VERIFIED: .planning/REQUIREMENTS.md:237-238]` — *"`prompts/documentation/HANDOFF.md` section
Lessons and `prompts/gsd-planning/HANDOFF.md` section Lessons."* — confirms sibling `HANDOFF.md`
files use named, addressable sections (a later requirement can say "add this to section X"),
which is the pattern this phase's `HANDOFF.md` should also follow so Phase 2/3 additions
(`MORNING100-60` adds to "Declared outputs", per the same citation) have a stable place to land.

### Anti-Patterns to Avoid
- **Writing Phase 2/3's clauses into `D01-dispatch.md` now:** the verification loop, the
  stop-on-broken-gate rule, and the automation boundary are `NIGHT100-30`/`NIGHT100-40`/
  `NIGHT100-50` — all Phase 2 — and each is independently cited as adding *into* the file this
  phase creates `[VERIFIED: .planning/REQUIREMENTS.md:184,191,199 — "in `prompts/delivery/D01-dispatch.md`"` three times]`. Scaffolding those clauses early creates content Phase 2 must then
  edit around rather than append to.
- **Assuming the round is a script/CLI command:** every "Creates" line in `REQUIREMENTS.md` for
  this kit names a `.md` file, never a `.sh`/`.mjs`/executable. The established convention across
  all three existing kits (`workshop-prep`, `documentation`, `gsd-planning`) is markdown prompt
  files invoked by the practitioner through their AI tool, not standalone scripts.

## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| Long-running/background process management for the overnight run | A bespoke daemon, custom polling loop, or hand-rolled process supervisor inside `D01-dispatch.md`'s prose | Whatever existing OS/CLI-native mechanism the practitioner's actual execution environment already provides (`tmux`/`screen` detached session, `nohup`, a systemd user service, or the AI CLI tool's own background/async run mode) `[ASSUMED]` | No source in this package names the execution substrate; hand-rolling a supervision mechanism in a markdown prompt file both guesses at infrastructure this phase doesn't own and duplicates what the OS or the AI tool already does |
| Severity/exit-condition logic for "when does the night stop" | Any bespoke pass/fail heuristic inside this phase's `D01-dispatch.md` | Nothing — this is explicitly out of scope for Phase 1; `NIGHT100-30`/`NIGHT100-40` (Phase 2) own it `[VERIFIED: .planning/ROADMAP.md:213-217]` | Building it now duplicates Phase 2's requirement and risks a competing, uncoordinated definition of "done for the night" |

**Key insight:** because this phase has no code, "hand-rolling" risk here is really *scope
creep into later phases' clauses*, not "reinventing a library." The single biggest hand-roll risk
is writing Phase 2/3/4/5 content into files this phase merely needs to create empty/skeletal.

## Finding: file absence confirmed for all three edit targets

`[VERIFIED: file absence confirmed via find(1) and ls(1) on 2026-09-28]` — ran from repo root:

```
$ find . -iname "PIPELINE.md" -not -path "*/.git/*"        → (no output)
$ find . -iname "HANDOFF.md"  -not -path "*/.git/*"        → (no output)
$ find . -type d -iname "prompts" -not -path "*/.git/*"    → (no output)
$ find . -iname "README.md"   -not -path "*/.git/*"        → ./README.md   (the generic GSD
                                                               handover README shown below —
                                                               NOT the five-stage front door
                                                               README.md the roadmap references)
```

The repository's only `README.md` (top level, 3020 bytes, confirmed by direct read this session)
is the GSD package's own handover instructions (*"Handover — a plan for changing the requirements
harness itself"*) — it contains no pipeline-stage language and is not the file `PLAN100-10`/
`NIGHT100-10` are meant to edit. This confirms the gap CONTEXT.md already flagged: **none of
`PIPELINE.md`, the real front-door `README.md`, or `prompts/documentation/HANDOFF.md` exist in
this repo as of this research session.** Do not treat this as a research failure — CONTEXT.md
names this the "Known gap — must close before planning finishes" and the user has already been
told to supply these files. The rest of this document's edit-site guidance is written to be
re-verified once real files land (see next section).

## Five-Stage → Six-Stage Edit Sites

The roadmap cites exact locations this phase must change, phrased as if the files already exist
with this content:

| File | Cited location | Roadmap's own words |
|---|---|---|
| `PIPELINE.md` (repo root) | line 3 | *"the five-stage claim at `PIPELINE.md:3`"* `[CITED: .planning/ROADMAP.md:203]` |
| `README.md` (repo root) | lines 6, 16, 27, 54 | *"at `README.md` lines 6, 16, 27 and 54"* `[CITED: .planning/ROADMAP.md:203]` |
| `prompts/documentation/HANDOFF.md` | line 192 | *"at `prompts/documentation/HANDOFF.md:192`"* `[CITED: .planning/ROADMAP.md:204]` |

**Since none of these three files exist yet in this repo, none of these exact line numbers or
wordings can be verified this session.** This table is a re-location checklist, not a confirmed
edit list: once the user supplies the real files, the planner/executor should first confirm the
cited line numbers still hold the five-stage claim the roadmap describes, using the line numbers
above as a sanity check that the supplied files match what the roadmap assumes — if a line number
is off, the files may be a different version than the one the roadmap's authors read, and the
five-stage claim should be re-located by content search (`five stages`, `5 stages`, a numbered
stage list ending at 5) rather than trusted by line number alone.

## Finding: what PLAN100-10 concretely creates

`[VERIFIED: .planning/REQUIREMENTS.md:153-156]` — full quote:
> "Closes the seam no row named. SITE100-10 carries the planning tool's output into the workbook;
> this row carries the same package on into build. NIGHT100-10 to NIGHT100-50 already hold what
> the run does — none of them states what the run is handed. **Creates the sixth-stage
> directory** and changes `PIPELINE.md` and `README.md`, which both declare five stages."

So `PLAN100-10`'s concrete deliverable is: **the `prompts/delivery/` directory itself**, plus the
`PIPELINE.md`/`README.md` edits. It does not create any round file on its own — that's
`NIGHT100-10`'s job (next finding).

## Finding: what NIGHT100-10 concretely creates

`[VERIFIED: .planning/REQUIREMENTS.md:163-165]` — full quote:
> "The single largest win the delivery team named. Removes the need for someone to be present
> pressing buttons and keeping a machine awake. Creates `prompts/delivery/D01-dispatch.md` and
> `prompts/delivery/HANDOFF.md`, reached by `PIPELINE.md` and `README.md`."

So `NIGHT100-10`'s concrete deliverables are **exactly two files**: `D01-dispatch.md` and
`HANDOFF.md`. "Reached by `PIPELINE.md` and `README.md`" means those two edited files must link
or point to the new stage — not merely rename "five" to "six" in prose, but also make the sixth
stage navigable/referenced the way the other five presumably already are (this cannot be confirmed
until the files are supplied, since their current five-stage cross-referencing style is unknown).

## Finding: D-02's "D04 to D06" describes the whole delivery kit, not this phase's output

This is the most important correction this research makes to the upstream planning package.

**The literal text of Decision 2** (both in `ROADMAP.md`'s open-decisions appendix and echoed in
CONTEXT.md's D-02) reads:

`[CITED: .planning/ROADMAP.md:184-194]` — *"...the round files run `D04` to `D06` rather than
sorting into the order the day runs them, because `D01` to `D03` were minted first and
renumbering them would churn four other rows for nothing; and `D06`, a reporting-and-handover
round, sits inside the delivery kit because the register proposes no reporting kit."*

Read in isolation, this could be misunderstood as "the round files **this phase** creates run D04
through D06." **That reading is wrong.** Direct verification against every "Creates
`prompts/delivery/D0N-...`" line in `REQUIREMENTS.md`, cross-checked against each requirement's
phase in the traceability table, gives the following complete, exhaustive map:

| Round file | Created by requirement | Requirement's phase | Verified citation |
|---|---|---|---|
| `D01-dispatch.md` | `NIGHT100-10` | **Phase 1 (this phase)** | `[VERIFIED: .planning/REQUIREMENTS.md:164]` — *"Creates `prompts/delivery/D01-dispatch.md`"* |
| `D02-morning-review.md` | `MORNING100-10` | Phase 3 | `[VERIFIED: .planning/REQUIREMENTS.md:208]` — *"`prompts/delivery/D02-morning-review.md`."* |
| `D03-session-pack.md` | `DEMO100-10` | Phase 4 | `[VERIFIED: .planning/REQUIREMENTS.md:256]` — *"Creates `prompts/delivery/D03-session-pack.md` as an"* |
| `D04-enter-overnight.md` | `NIGHT100-20` | Phase 2 | `[VERIFIED: .planning/REQUIREMENTS.md:173]` — *"Creates `prompts/delivery/D04-enter-overnight.md`."* |
| `D05-leave-overnight.md` | `MORNING100-20` | Phase 3 | `[VERIFIED: .planning/REQUIREMENTS.md:216]` — *"`prompts/delivery/D05-leave-overnight.md`."* |
| `D06-weekly-status.md` | `REPORT100-10` | Phase 5 | `[VERIFIED: .planning/REQUIREMENTS.md:295]` — *"`prompts/delivery/D06-weekly-status.md` as the"* |

Phase assignment for each requirement `[VERIFIED: .planning/REQUIREMENTS.md:379-395]`, quoting
the exact traceability-table rows:
> "| PLAN100-10 | `CR-080` | Phase 1 | Pending |" (line 379)
> "| NIGHT100-10 | `CR-090` | Phase 1 | Pending |" (line 380)
> "| NIGHT100-20 | `CR-100` | Phase 2 | Pending |" (line 381)
> "| MORNING100-10 | `CR-140` | Phase 3 | Pending |" (line 385)
> "| MORNING100-20 | `CR-150` | Phase 3 | Pending |" (line 386)
> "| DEMO100-10 | `CR-200` | Phase 4 | Pending |" (line 391)
> "| REPORT100-10 | `CR-240` | Phase 5 | Pending |" (line 395)

**Conclusion:** Decision 2's "D04 to D06" phrase describes the *numbering range that exists
across the whole six-file delivery kit* (spanning Phases 1 through 5), and explains *why the
numbers don't sort into day-run order* (D01=dispatch/evening, D04=enter-overnight/evening,
[verification loop overnight], D05=leave-overnight/morning, D02=morning-review/morning, …,
D03=session-pack/midday demo, D06=weekly-status/periodic — the numbers were minted in registration
order, not run order). It is **not** an instruction that Phase 1 itself produces four files.
**Phase 1 produces exactly one round file: `D01-dispatch.md`.** The planner must not schedule
tasks to create `D02`, `D03`, `D04`, `D05`, or `D06` in this phase — those belong to their own
phases above.

Also note: `NIGHT100-30` (line 184), `NIGHT100-40` (line 191), and `NIGHT100-50` (line 199) — all
Phase 2 requirements — each add a *clause* into the same `D01-dispatch.md` this phase creates
(the verification loop, the stop-on-broken-gate rule, and the automation boundary,
respectively). This confirms the "leave room for Phase 2 to append" guidance already given in
Architecture Patterns above: `D01-dispatch.md`'s Phase-1 content should state what NIGHT100-10
itself requires (received input, dispatch action) without trying to pre-empt those three clauses.

## What "dispatch at day's end" concretely requires to implement

**Grounded in the requirement cards (not assumed):**
- `[VERIFIED: analysis/requirement-detail/NIGHT100-10.md]` — quote: *"But like the big wins for us
  would be automation. So when we close the computers at 5 o'clock in the evening, we want things
  to happen."* — the delivery lead, `S-01 25:16`–`25:21`.
- `[CITED: .planning/ROADMAP.md:173]` — Success Criterion 3: *"The practitioner runs one dispatch
  round at the end of a working day and leaves; the work continues without anyone pressing
  buttons or keeping a machine awake."*
- `[CITED: .planning/REQUIREMENTS.md:163-164]` — *"Removes the need for someone to be present
  pressing buttons and keeping a machine awake."*

**What these three sources jointly establish, without assumption:**
1. The trigger is one manual round invocation, not a cron/scheduler (`D-04`, locked).
2. The round itself is a markdown prompt file (`D01-dispatch.md`), following the established
   sibling convention — not a shell script, not a compiled binary (see Architecture Patterns →
   Anti-Patterns above).
3. Whatever runs after dispatch must **not** require "keeping a machine awake" — i.e., the
   design must not depend on the practitioner's own laptop staying open/unlocked overnight. The
   phrase "when we close the computers" (plural, delivery team's computers) describes the
   computers going offline at 5pm, which is incompatible with the overnight run being a foreground
   or even backgrounded-but-still-attached process on that same hardware.

**What is genuinely unresolved (no source states this — flagged, not guessed as fact):**
- **`[ASSUMED]`** Nothing in `PLAN100-10`, `NIGHT100-10`, their cards, CONTEXT.md, or ROADMAP.md
  names the actual execution substrate for the overnight run — not a remote server, not a cloud
  sandbox, not a CI runner, not the practitioner's own machine kept alive by some other means.
  Common approaches an unattended-agent-run implementation could use, none of them confirmed for
  this project: a detached `tmux`/`screen` session on a machine that *does* stay powered on (a
  workstation distinct from "the computers" that get closed), a `nohup`-backgrounded process, a
  systemd user service/timer, a queued job on a CI-like runner (e.g., a scheduled or
  manually-dispatched GitHub Actions workflow), or the AI CLI tool's own native background/async
  run mode if the practitioner's tool of choice has one.
- This is squarely a Phase 1 concern (Success Criterion 3 is in this phase, not Phase 2), yet the
  requirement card's own "Open items and watch-outs" section is silent on it — it only says *"A
  dispatch is only as safe as the bounds around it, and those are four separate requirements"*
  `[VERIFIED: analysis/requirement-detail/NIGHT100-10.md]`, which is about safety bounds
  (Phase 2's job), not about where the process physically runs.
- **Recommendation:** raise this as a `checkpoint:human-verify` question before or during
  planning — "what machine/service actually keeps running after the practitioner leaves?" —
  rather than have the plan silently assume a specific substrate. `D01-dispatch.md`'s Phase-1
  content can reasonably document the *contract* (what's handed in, that a dispatch happens) while
  explicitly marking the execution substrate as a documented open item for the practitioner to
  fill in, rather than fabricating an answer.

## Risk R-080 implications for this phase's plan

Per D-03 (locked, applies to all eight phases): every requirement in this engagement — including
both of this phase's — changes the harness that is shown to clients, while the harness is used to
change itself. This is a cross-cutting concern, not unique to Phase 1, so this note is
intentionally brief:

- **Don't default to auto-merge/auto-publish of this phase's edits.** A `PIPELINE.md`/`README.md`
  edit that's wrong (e.g., using the wrong stage name, or a bad line-number-based edit that
  corrupts unrelated content) would, per the roadmap's own words, *"reach the template's default
  branch"* and "reach every other engagement's live site too" `[CITED: .planning/ROADMAP.md, Open
  decisions, Decision 5 row]`. Plans for this phase should include a human review step (or at
  minimum a diff-review checkpoint) before these root-level docs are committed to a shared/default
  branch, rather than a fully automated commit-and-push.
- **The brake exists but isn't active tooling yet:** the roadmap names `.handover-freeze` (branch
  level) and `.handover-freeze-all` (default-branch level) as the mechanism to halt propagation if
  needed `[CITED: .planning/ROADMAP.md, Open decisions, Decision 5 row]`. This phase does not need
  to build that mechanism (it's not one of this phase's two requirements), but the planner should
  be aware it's the named escape hatch if this phase's edits need to be walked back after landing.
- No further action is required of Phase 1 beyond normal review discipline — R-080 is a stance,
  not a deliverable this phase owns.

## Common Pitfalls

### Pitfall 1: Scaffolding D02–D06 in this phase
**What goes wrong:** the planner reads CONTEXT.md's D-02 ("round files run D04 to D06...") at
face value and creates four extra round files in `prompts/delivery/` during Phase 1.
**Why it happens:** the decision text describes the *numbering scheme* for the whole six-file kit,
not this phase's specific output, and is easy to misread in isolation.
**How to avoid:** only create `D01-dispatch.md` and `HANDOFF.md` in this phase; cross-check
against the phase-to-file map in `## Finding: D-02's "D04 to D06"...` above before writing any
task that creates a `prompts/delivery/D0N-*.md` file.
**Warning signs:** a task list for this phase that names more than one round file, or names any
of `D02`, `D03`, `D04`, `D05`, `D06`.

### Pitfall 2: Writing Phase 2's clauses into D01-dispatch.md now
**What goes wrong:** since `D01-dispatch.md` is the file the verification loop, stop-on-gate rule,
and automation boundary all get added to later, a planner might try to write those clauses now
"while we're in the file anyway."
**Why it happens:** it feels efficient to finish the file in one pass.
**How to avoid:** scope Phase 1's edit to what `NIGHT100-10` itself requires (dispatch entry
point, what it's handed) and leave clearly-marked, named sections for Phase 2 to append into
(mirroring the "Declared outputs" / "Lessons" named-section convention verified above), rather
than pre-writing Phase 2's content.
**Warning signs:** `D01-dispatch.md` in this phase's plan already contains attempt-count bounds,
gate-break behavior, or an automation/human boundary list — those are `NIGHT100-30`/`-40`/`-50`.

### Pitfall 3: Editing files that don't exist based on assumed wording
**What goes wrong:** the planner writes an edit task like "change line 3 of PIPELINE.md from
'five stages' to 'six stages'" as if the file's current wording is already known.
**Why it happens:** the roadmap's confident, specific line citations (`PIPELINE.md:3`,
`README.md:6,16,27,54`, `prompts/documentation/HANDOFF.md:192`) read like verified facts.
**How to avoid:** treat every cited line number as a **re-location hint**, not a confirmed fact,
until the user supplies the real files (see `## Five-Stage → Six-Stage Edit Sites`). Re-verify by
content search first.
**Warning signs:** a plan step that edits a file this research confirmed does not exist yet,
without a preceding step to obtain/confirm that file's real content.

### Pitfall 4: Designing the dispatch round as a foreground/local process
**What goes wrong:** `D01-dispatch.md` is written as if invoking it starts a process that must
keep the practitioner's terminal or laptop open to survive until morning.
**Why it happens:** without an explicit execution-substrate decision, "just run it and see" is the
easiest default.
**Why it's wrong here:** the source evidence explicitly says the computers are closed at 5pm
(see `## What "dispatch at day's end" concretely requires`) — a design that depends on that same
machine staying awake contradicts the requirement's own stated premise.
**How to avoid:** flag the execution substrate as an open question for the user rather than
silently picking "run it in my terminal and leave the laptop open."

### Pitfall 5: Auto-merging this phase's edits without review
**What goes wrong:** committing and merging `PIPELINE.md`/`README.md`/`HANDOFF.md` edits straight
to a shared/default branch with no review step, given this phase's own edits are exactly the kind
of harness self-modification R-080 names as a live risk.
**How to avoid:** see `## Risk R-080 implications` above — include a review/diff-check step before
these root-level docs land on a branch other engagements might inherit from.

### Pitfall 6: Confusing "eight stages" with "five/six stages"
**What goes wrong:** `REQUIREMENTS.md` itself says *"Section headings are the process stages of
the decomposition record... Seven of the eight stages carry rows"* `[VERIFIED:
.planning/REQUIREMENTS.md:59-60]` — this "eight stages" describes the requirements-analysis
process's own section structure (Workshop capture, Requirements documentation, Planning and
roadmap, Autonomous build, Morning review, Daily demo and feedback, Handover site, Hardening —
roughly), a completely different count from the pipeline's five-going-on-six *runtime* stages
this phase edits. Do not conflate the two when searching `PIPELINE.md`/`README.md` for the
five-stage claim.

## Code Examples

All examples below are **proposed skeletons for files that must be created or edited**, not
verbatim excerpts of real content (the target files don't exist / aren't supplied yet). They are
`[ASSUMED]` structure, grounded only in the section names and contracts verified above.

### `prompts/delivery/HANDOFF.md` skeleton
```markdown
# Delivery stage — HANDOFF

## What this stage is handed
- The signed requirements package, carried from the planning tool with no manual step
  (PLAN100-10). [Confirm exact package format/location once SITE100-10's output is defined.]

## Declared outputs
<!-- MORNING100-60 (Phase 3) appends to this section later — keep it a stable, named anchor -->
- A dispatched overnight build run (this phase's contribution).
```

### `prompts/delivery/D01-dispatch.md` skeleton
```markdown
# D01 — Dispatch

**Invoked by:** the practitioner, manually, at the end of the working day (D-04 — not a
scheduled/cron trigger).

**Receives:** the signed requirements package (see HANDOFF.md).

**Does:** dispatches the day's agreed work into the delivery build so it can run unattended
overnight.

<!--
  Phase 2 appends here:
  - NIGHT100-30: verification-loop / exit-condition clauses
  - NIGHT100-40: stop-on-broken-gate clause
  - NIGHT100-50: automation boundary (permitted vs. reserved acts)
  Do not pre-write these in Phase 1.
-->

**Execution substrate:** <!-- OPEN QUESTION — not specified by any source in this package; do not
  fabricate an answer here. Confirm with the practitioner before or during Phase 1 planning. -->
```

### `PIPELINE.md` stage-list edit pattern (illustrative — exact current wording unknown)
```markdown
<!-- BEFORE (assumed shape, unverified — file does not exist in this repo yet) -->
This pipeline has five stages: ... , ending at the handover site.

<!-- AFTER -->
This pipeline has six stages: ... , the sixth being the delivery build in `prompts/delivery/`
that continues past the handover site.
```

## State of the Art

Not applicable in the conventional "library/version" sense — there is no prior version of this
pipeline's sixth stage to compare against; it doesn't exist yet. The one relevant "before/after"
is the pipeline's own stage count, already covered in `## Five-Stage → Six-Stage Edit Sites`.

## Assumptions Log

| # | Claim | Section | Risk if Wrong |
|---|-------|---------|---------------|
| A1 | The execution substrate for the overnight run is not the practitioner's own laptop (since it's closed at 5pm) — but *what* it is instead is unnamed by any source | What "dispatch at day's end" concretely requires | Plan may build a round file whose implicit design (foreground/attached process) can never satisfy Success Criterion 3; needs practitioner input before or during planning |
| A2 | Common unattended-execution mechanisms (tmux/screen, nohup, systemd user service, CI runner, AI-tool-native background mode) are the plausible design space | What "dispatch at day's end" concretely requires / Don't Hand-Roll | If the practitioner already has a specific mechanism in mind (e.g., a specific CI system already in use elsewhere in the org), guessing wrong wastes a planning cycle |
| A3 | `D01-dispatch.md`'s Phase-1 content should be scoped to contract + dispatch action only, leaving named sections for Phase 2 to append clauses into | Architecture Patterns, Pitfall 2 | If Phase 2's plan doesn't actually append into the same file (e.g., splits into a separate file instead), this phase's "leave room" design adds unused structure — low risk, cheap to fix |
| A4 | The code skeletons in `## Code Examples` are a reasonable minimal shape for `HANDOFF.md`/`D01-dispatch.md` | Code Examples | If the user's real sibling `HANDOFF.md` files (once supplied) use a substantially different section vocabulary, this phase's file should match the real siblings, not this proposed skeleton |

**None of the two locked-decision claims (D-01 directory name, D-04 manual trigger) are in this
table** — those are CONTEXT.md decisions, already user-facing and flagged as "assumption made
under autopilot" in their own text; this research does not add new assumption risk to them, only
carries them forward verbatim.

## Open Questions

1. **What is the actual execution substrate for the overnight run?**
   - What we know: it's not a scheduled/cron trigger (D-04), and it can't depend on the
     practitioner's own machine staying awake (per the source evidence).
   - What's unclear: whether it's a shared team server, a cloud sandbox, a CI-like runner, or
     something else — no source in this package says.
   - Recommendation: raise with the user as a `checkpoint:human-verify` before finalizing Phase 1's
     plan; do not let the plan silently assume a specific mechanism.

2. **What exact content do `PIPELINE.md`, `README.md`, and `prompts/documentation/HANDOFF.md`
   currently carry?**
   - What we know: the roadmap names precise line numbers for a "five stages" claim in each.
   - What's unclear: everything about their actual current wording, since none of the three files
     exist in this repo yet.
   - Recommendation: block the exact edit-diff tasks on the user supplying these files; use the
     cited line numbers only as a sanity check once supplied, per `## Five-Stage → Six-Stage Edit
     Sites`.

3. **Does the sibling `HANDOFF.md` convention (once the real `prompts/documentation/HANDOFF.md` is
   supplied) use section names beyond "Declared outputs" and "Lessons" that this phase's new
   `HANDOFF.md` should also adopt for consistency?**
   - What we know: two section names are directly cited (`Declared outputs`, `Lessons`).
   - What's unclear: the full section list/order of a real `HANDOFF.md` file.
   - Recommendation: once `prompts/documentation/HANDOFF.md` is supplied, mirror its full section
     structure rather than inventing a new shape from the two known section names alone.

## Environment Availability

| Dependency | Required By | Available | Version | Fallback |
|------------|------------|-----------|---------|----------|
| git | committing this phase's file edits | ✓ | 2.55.0 | — |
| Web search / Context7 / any MCP research provider | researching "unattended overnight agent execution" patterns (item 2 of this phase's research scope) | ✗ | — | None in this session — `.planning/config.json` has `brave_search`, `firecrawl`, `exa_search`, `tavily_search`, `ref_search`, `perplexity`, and `jina` all set to `false`, and no `WebSearch`/`WebFetch`/MCP tool is present in this agent's toolset. The `gsd_run query research-plan` seam was invoked and correctly proposed a `websearch` fetch for both research questions, but no tool exists to execute it this session. Findings on execution-substrate patterns above are therefore `[ASSUMED]` from training knowledge, not fetched or verified this session. |
| `tmux`, `nohup` (illustrative — not confirmed as *this project's* chosen mechanism) | possible overnight-run substrate options named in Don't Hand-Roll | ✓ (both present on this research machine) | — | Irrelevant until Open Question 1 is answered — presence here says nothing about the target deployment environment |

**Missing dependencies with no fallback:**
- None that block this phase's actual deliverables (directory + two edited/created markdown
  files + three text edits). The missing web-search capability only affects the depth of the
  "state of the art for overnight agent execution" side-research, which this document already
  flags as `[ASSUMED]` rather than treating as a blocker.

**Missing dependencies with fallback:**
- Web search unavailable → training-knowledge-based `[ASSUMED]` findings, clearly tagged
  throughout, with Open Question 1 raised for explicit user confirmation rather than silently
  resolved.

## Validation Architecture

`workflow.nyquist_validation` is `true` in `.planning/config.json` (confirmed by direct read this
session), so this section is included. There is no code and no existing test framework in this
repo — the appropriate "test" for a documentation/scaffolding phase is file-existence and
content-grep assertions, not unit tests.

### Test Framework
| Property | Value |
|----------|-------|
| Framework | none — shell-based file-existence/content assertions (`test -f`, `grep -q`) |
| Config file | none — see Wave 0 |
| Quick run command | `test -d prompts/delivery && test -f prompts/delivery/D01-dispatch.md && test -f prompts/delivery/HANDOFF.md` |
| Full suite command | see Phase Requirements → Test Map below, run as one shell script |

### Phase Requirements → Test Map
| Req ID | Behavior | Test Type | Automated Command | File Exists? |
|--------|----------|-----------|-------------------|-------------|
| PLAN100-10 | Sixth-stage directory exists | smoke | `test -d prompts/delivery` | ❌ Wave 0 |
| PLAN100-10 | `PIPELINE.md` declares six stages, not five | smoke | `grep -qi "six stages" PIPELINE.md && ! grep -qi "five stages" PIPELINE.md` | ❌ Wave 0 (file doesn't exist — blocked until user supplies it) |
| PLAN100-10 | `README.md` (real front-door one, not the GSD handover one) declares six stages at all four cited lines | smoke | `grep -n "stage" README.md \| head -20` (manual re-check of lines 6/16/27/54 after edit) | ❌ Wave 0 (file doesn't exist yet) |
| NIGHT100-10 | `D01-dispatch.md` exists and states what it's handed | smoke | `test -f prompts/delivery/D01-dispatch.md && grep -qi "handed\|receives" prompts/delivery/D01-dispatch.md` | ❌ Wave 0 |
| NIGHT100-10 | `prompts/delivery/HANDOFF.md` exists with a "Declared outputs" section | smoke | `test -f prompts/delivery/HANDOFF.md && grep -qi "declared outputs" prompts/delivery/HANDOFF.md` | ❌ Wave 0 |
| NIGHT100-10 | Overnight-unattended behavior actually works (survives practitioner leaving) | manual-only | — (cannot be automated until Open Question 1 is resolved) | ❌ manual-only, justified: no execution substrate is defined yet, so there is nothing to script against |

### Sampling Rate
- **Per task commit:** run the quick smoke check above (file existence).
- **Per wave merge:** run the full grep-based content-check script once all edit tasks land.
- **Phase gate:** all smoke checks green, plus a human confirms the `PIPELINE.md`/`README.md`
  wording reads correctly (this is prose, not logic — a human read is the real gate here) before
  `/gsd-verify-work`.

### Wave 0 Gaps
- [ ] The three edit-target files (`PIPELINE.md`, `README.md`, `prompts/documentation/HANDOFF.md`)
      must be supplied by the user before any edit task (not just test) can run — this blocks
      Wave 0 entirely for the edit half of this phase.
- [ ] No shared shell test-runner script exists yet for this repo's documentation-smoke checks —
      consider a small `scripts/check-pipeline-stages.sh` (or similar) as a Wave 0 task if this
      pattern will be reused by later phases' own five/six-stage-adjacent checks.

## Security Domain

`security_enforcement` is `true` (ASVS level 2, block on `high`) in `.planning/config.json`,
confirmed by direct read this session, so this section is included. This phase has no
authentication, session, or user-input-processing surface in the conventional web-application
sense — it edits static Markdown files in a git repository.

### Applicable ASVS Categories

| ASVS Category | Applies | Standard Control |
|---------------|---------|-----------------|
| V2 Authentication | no | n/a — no login/identity surface created by this phase |
| V3 Session Management | no | n/a |
| V4 Access Control | no | n/a — git's own branch/commit access control governs who can edit these files, unchanged by this phase |
| V5 Input Validation | marginal | The "input" here is prompt/markdown content itself, invoked by an AI CLI tool. A round file (`D01-dispatch.md`) that an AI agent reads and acts on is a prompt-injection surface if its content can be influenced by untrusted sources; keep the file's content limited to instructions the practitioner/team controls directly (no verbatim inclusion of unreviewed external text) |
| V6 Cryptography | no | n/a — no secrets or crypto introduced by this phase |

### Known Threat Patterns for this stack

| Pattern | STRIDE | Standard Mitigation |
|---------|--------|---------------------|
| Uncontrolled harness self-modification reaching the default branch and every client engagement built from it (R-080) | Tampering | Human review/diff-check before merging this phase's `PIPELINE.md`/`README.md`/`HANDOFF.md` edits to a shared/default branch; the `.handover-freeze`/`.handover-freeze-all` mechanism named in ROADMAP.md's Decision 5 row is the documented escape hatch if a bad change needs to be halted `[CITED: .planning/ROADMAP.md, Open decisions, Decision 5 row]` |
| A round file (`D01-dispatch.md`) that an unattended agent reads and acts on being corrupted or tampered with before an overnight run starts | Tampering | Treat round files as reviewed configuration, not runtime-generated content; commit them through the same review gate as the rest of the harness rather than allowing an earlier automated step to rewrite them unsupervised |

## Sources

### Primary (HIGH confidence — direct read of this repo's own source-of-truth files this session)
- `.planning/phases/01-open-the-sixth-stage-and-dispatch-the-night/01-CONTEXT.md` — locked
  decisions, discretion areas, deferred ideas (read in full this session)
- `.planning/ROADMAP.md` — Phase 1 section (lines 165–204) and Open decisions appendix (lines
  478–503), read directly this session
- `.planning/REQUIREMENTS.md` — full "Creates ..." attribution for every delivery-kit round file,
  the traceability table (phase assignments), and the header/legend sections, read directly this
  session
- `analysis/requirement-detail/PLAN100-10.md` and `analysis/requirement-detail/NIGHT100-10.md` —
  read in full this session
- `.planning/PROJECT.md` — Key Decisions table row on the R-080 self-modification risk, and the
  "What This Is" / scope sections, read directly this session
- `.planning/config.json` — `workflow.nyquist_validation` and `workflow.security_enforcement`
  flags, read directly this session
- Direct filesystem probes this session (`find`, `ls`) confirming `PIPELINE.md`, `prompts/`, and
  `HANDOFF.md` are absent from this repository, and that the existing top-level `README.md` is
  the GSD handover README, not a five-stage front door

### Secondary (MEDIUM confidence)
- None — no external documentation or web source was reachable this session (see Environment
  Availability).

### Tertiary (LOW confidence — training knowledge only, not fetched or verified this session)
- General patterns for unattended/background execution of long-running processes (detached
  terminal multiplexers, `nohup`, systemd user services, CI-runner scheduled/dispatched jobs, AI
  CLI tools' own async/background modes) — `[ASSUMED]`, see `## What "dispatch at day's end"
  concretely requires` and Assumptions Log A1/A2. Flagged for user confirmation rather than
  presented as settled.

## Metadata

**Confidence breakdown:**
- In-repo planning-package facts (what each requirement creates, phase assignments, sibling-kit
  conventions): HIGH — every claim traced to a specific file and line, read directly this
  session, with verbatim quotes.
- File-absence finding (PIPELINE.md/README.md/HANDOFF.md/prompts/ don't exist): HIGH — confirmed
  by direct `find`/`ls` probes this session, matches CONTEXT.md's own flagged gap.
- Execution-substrate / "how does unattended overnight AI execution actually work" domain: LOW —
  no source in this package answers it, and no web-search tool was available this session to
  investigate external prior art. Treated as an Open Question, not resolved.
- Exact wording of the three files this phase edits: NONE — files don't exist yet; this is
  explicitly out of scope for this research and handed to the user per CONTEXT.md's known gap.

**Research date:** 2026-09-28
**Valid until:** Effectively indefinite for the in-repo findings (they're static planning-package
text, re-verify only if `.planning/*.md` files change upstream). The execution-substrate Open
Question has no expiry — it stays open until the user answers it, independent of any calendar
date.
