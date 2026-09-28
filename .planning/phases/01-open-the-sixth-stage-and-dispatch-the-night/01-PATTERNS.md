# Phase 1: Open the sixth stage and dispatch the night - Pattern Map

**Mapped:** 2026-09-28
**Files analyzed:** 5 (2 new, 3 edited)
**Analogs found:** 0 / 5

## Headline finding: no analogs exist anywhere in this repository

This phase is pure Markdown repository scaffolding — no framework, no library, no runtime code.
Verified this session:

```
$ git ls-files | sort
.planning/phases/01-open-the-sixth-stage-and-dispatch-the-night/01-CONTEXT.md
.planning/phases/01-open-the-sixth-stage-and-dispatch-the-night/01-DISCUSSION-LOG.md
.planning/phases/01-open-the-sixth-stage-and-dispatch-the-night/01-RESEARCH.md
.planning/STATE.md
README.md
```

`.planning/PROJECT.md`, `.planning/ROADMAP.md`, `.planning/REQUIREMENTS.md`,
`.planning/config.json`, and every file under `analysis/requirement-detail/` are **untracked**
(`git status` shows them `??`) — not gitignored mirrors, just not yet committed. None of them are
code analogs; they are the planning package itself (read-only inputs to this phase, not files
this phase's plans copy structure from).

Directory/file searches for every file this phase's requirements touch confirm **total absence**:

```
$ find . -iname "PIPELINE.md"        -not -path "*/.git/*"   → (no output)
$ find . -iname "HANDOFF.md"         -not -path "*/.git/*"   → (no output)
$ find . -type d -iname "prompts"    -not -path "*/.git/*"   → (no output)
```

The only tracked `README.md` (repo root) is the GSD handover README (*"Handover — a plan for
changing the requirements harness itself"*) — a different document from the five-stage front-door
`README.md` this phase's `PLAN100-10`/`NIGHT100-10` requirements describe editing. It carries no
pipeline-stage content and is not a usable analog for that edit.

**None of the three sibling kit directories the roadmap's own text references as the naming
convention (`prompts/workshop-prep/`, `prompts/documentation/`, `prompts/gsd-planning/`) exist in
this repo either.** They are referenced only in the planning package's prose (`REQUIREMENTS.md`),
not present as real files to read. There is nothing on disk, in any role (controller, component,
service, config, etc.), that this phase's five target files can be said to structurally resemble.

**Consequence for the planner:** every file below has **no analog**. Plans must build these files
from the verified requirement-card quotes and the `[ASSUMED]` skeletons in `01-RESEARCH.md`'s
`## Code Examples` section, not from copied code. This is expected and stated as a known gap in
`01-CONTEXT.md` ("Known gap — must close before planning finishes") and confirmed independently by
this pattern-mapping pass — it is not a research or mapping failure.

## File Classification

| New/Modified File | Role | Data Flow | Closest Analog | Match Quality |
|---|---|---|---|---|
| `prompts/delivery/D01-dispatch.md` | prompt/round file (nearest role: **config** — declarative instruction file, no execution logic of its own) | event-driven (manually triggered, runs unattended after) | none | no analog |
| `prompts/delivery/HANDOFF.md` | contract/interface doc (nearest role: **config**) | request-response (declares input contract / output contract between stages) | none | no analog |
| `PIPELINE.md` (repo root) | manifest/config | transform (edit in place: "five" → "six") | none | no analog |
| `README.md` (repo root, front-door variant — **not** the currently-tracked GSD handover README) | documentation/config | transform (edit in place, 4 line sites) | none | no analog |
| `prompts/documentation/HANDOFF.md` | contract/interface doc (nearest role: **config**) | transform (edit in place, 1 line site) | none | no analog |

**Note on `README.md`:** the repo already has a tracked `README.md`, but per `01-CONTEXT.md` and
`01-RESEARCH.md` this is a *different* file in content from the one the roadmap describes editing
(the front-door, five-stages-declaring README). Do not treat the currently-tracked `README.md` as
the analog for itself — its current content is out of scope for this phase's edit until the user
supplies the real front-door file, per the Known Gap.

## Pattern Assignments

Because no analog exists for any of the five files, "Pattern Assignments" below point to the
**verified requirement-card text and the research's `[ASSUMED]` skeletons** as the only available
concrete basis — flagged explicitly as not-a-code-copy, per the read-only/no-fabrication
constraint.

### `prompts/delivery/D01-dispatch.md` (new)

**Analog:** none (no round file / prompt file of any kind exists anywhere in this repo yet).

**Basis to build from instead — verified source text:**

`analysis/requirement-detail/NIGHT100-10.md` (full card, verified read this session) is the
authoritative content source. Key excerpt (evidence quote, use verbatim where the round file
should attribute its own trigger rationale):

> "But like the big wins for us would be automation. So when we close the computers at 5 o'clock
> in the evening, we want things to happen."
> — the delivery lead, `S-01 25:16`–`25:21`

**Structural skeleton** (from `01-RESEARCH.md` lines 510-529, marked `[ASSUMED]` — not verified
against a real file, since none exists):
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

**Must-not-do (verified, not assumed):** do not write `NIGHT100-30`/`NIGHT100-40`/`NIGHT100-50`
clauses (verification loop, stop-on-broken-gate, automation boundary) into this file now — those
are Phase 2 requirements that append to this same file later
(`[VERIFIED: .planning/REQUIREMENTS.md:184,191,199]`).

---

### `prompts/delivery/HANDOFF.md` (new)

**Analog:** none directly present, but the planning package's own text names a **structural
convention** (not a copyable file) shared by sibling kits — cited here as the closest thing to a
pattern reference, clearly labeled as *prose describing an absent file*, not code:

`[VERIFIED: .planning/REQUIREMENTS.md:142,144]`:
```
`prompts/documentation/HANDOFF.md`, `P-GEN-05-validate.md`, ...
`prompts/gsd-planning/HANDOFF.md`, `prompts/gsd-planning/P00-intake.md`, ...
```
This confirms every existing kit has its own per-stage `HANDOFF.md` (not one pipeline-wide file) —
apply the same placement to `prompts/delivery/HANDOFF.md`.

`[VERIFIED: .planning/REQUIREMENTS.md:245-246]` confirms the section name at least one sibling
`HANDOFF.md` uses: **"Declared outputs"** — literally cited as a named, addressable section that a
later requirement (`MORNING100-60`, Phase 3) appends into. Use this exact section name so Phase 3
has a stable anchor.

`[VERIFIED: .planning/REQUIREMENTS.md:237-238]` confirms a second sibling section name pattern:
**"Lessons"** (used by `prompts/documentation/HANDOFF.md` and `prompts/gsd-planning/HANDOFF.md`) —
optional to mirror, not required by this phase's requirements, but consistent with the convention.

**Structural skeleton** (from `01-RESEARCH.md` lines 497-508, `[ASSUMED]`):
```markdown
# Delivery stage — HANDOFF

## What this stage is handed
- The signed requirements package, carried from the planning tool with no manual step
  (PLAN100-10). [Confirm exact package format/location once SITE100-10's output is defined.]

## Declared outputs
<!-- MORNING100-60 (Phase 3) appends to this section later — keep it a stable, named anchor -->
- A dispatched overnight build run (this phase's contribution).
```

---

### `PIPELINE.md` (repo root, edit — file currently MISSING)

**Analog:** none. File does not exist in this repo. Confirmed by `find . -iname "PIPELINE.md"`
returning no output.

**Edit site** (per roadmap, unverifiable until the user supplies the file):
`[CITED: .planning/ROADMAP.md:203]` — *"the five-stage claim at `PIPELINE.md:3`"*.

**Illustrative edit pattern** (from `01-RESEARCH.md` lines 534-541, explicitly `[ASSUMED]` —
exact current wording unknown):
```markdown
<!-- BEFORE (assumed shape, unverified — file does not exist in this repo yet) -->
This pipeline has five stages: ... , ending at the handover site.

<!-- AFTER -->
This pipeline has six stages: ... , the sixth being the delivery build in `prompts/delivery/`
that continues past the handover site.
```

**Action required before this edit can be planned concretely:** the user must supply this file.
Once supplied, re-locate the five-stage claim by content search (`five stages`, `5 stages`, a
numbered stage list ending at 5) rather than trusting line 3 by number alone, per
`01-RESEARCH.md`'s own re-verification guidance.

---

### `README.md` (repo root, edit — front-door variant currently MISSING)

**Analog:** none. The currently-tracked `README.md` is a different document (GSD handover README)
and is not the analog for its own future edit — do not use it as a structural reference for the
five-stage front-door content.

**Edit sites** (per roadmap, unverifiable until the user supplies the file):
`[CITED: .planning/ROADMAP.md:203]` — *"at `README.md` lines 6, 16, 27 and 54"*.

**Action required before this edit can be planned concretely:** same as `PIPELINE.md` above — user
supplies the file; re-locate the five-stage claim by content search once supplied.

---

### `prompts/documentation/HANDOFF.md` (edit — file currently MISSING, sibling directory also absent)

**Analog:** none. Neither the file nor its parent directory (`prompts/documentation/`) exists in
this repo. Confirmed by `find . -type d -iname "prompts"` returning no output.

**Edit site** (per roadmap, unverifiable until the user supplies the file):
`[CITED: .planning/ROADMAP.md:204]` — *"at `prompts/documentation/HANDOFF.md:192`"*.

**Note:** this file is also referenced as the *convention source* for `prompts/delivery/HANDOFF.md`
above (its "Declared outputs" and "Lessons" section names are cited in `REQUIREMENTS.md`), but its
actual content cannot be read — it doesn't exist. Treat the section-name citations as the only
verified fragment; everything else about this file is unknown until supplied.

**Action required before this edit can be planned concretely:** user supplies the file; re-locate
the five-stage claim by content search once supplied (line 192 is a sanity check only).

## Shared Patterns

### No shared code pattern applies (no auth, no error handling, no validation layer)

This phase produces no application code, so the usual cross-cutting concerns (auth middleware,
error handling wrappers, response formatting, DB transactions) do not apply. The only genuinely
cross-cutting concern across all five files is a **naming/reference discipline**, not a code
pattern:

### Cross-file consistency: "six stages" must land identically in all three edited files
**Source:** requirement text only (no code source) —
`[VERIFIED: .planning/REQUIREMENTS.md:153-156]` (PLAN100-10) and
`[VERIFIED: .planning/REQUIREMENTS.md:163-165]` (NIGHT100-10).
**Apply to:** `PIPELINE.md`, `README.md` (4 sites), `prompts/documentation/HANDOFF.md`.
**Rule:** all edits must consistently say "six stages" (not a mix of "six" and leftover "five"
language), and `PIPELINE.md`/`README.md` must be made to reference/link the new
`prompts/delivery/` stage the same way the existing five stages are presumably cross-referenced —
confirm the existing cross-reference style once the files are supplied, don't invent one.

### Cross-file consistency: stable, named `HANDOFF.md` sections
**Source:** `[VERIFIED: .planning/REQUIREMENTS.md:245-246, 237-238]`.
**Apply to:** `prompts/delivery/HANDOFF.md`.
**Rule:** use the section name **"Declared outputs"** verbatim (Phase 3's `MORNING100-60` appends
to it later) and consider **"Lessons"** for consistency with sibling kits. Do not restructure or
rename these sections once created — later phases append into them by name.

### Cross-file consistency: do not pre-write later phases' clauses
**Source:** `[VERIFIED: .planning/REQUIREMENTS.md:184,191,199]`.
**Apply to:** `prompts/delivery/D01-dispatch.md`.
**Rule:** leave clearly marked insertion points (e.g. HTML comments) for Phase 2's three
appended clauses; do not draft their content now.

## No Analog Found

All five files in scope for this phase have no analog anywhere in the tracked or untracked
repository contents.

| File | Role | Data Flow | Reason |
|---|---|---|---|
| `prompts/delivery/D01-dispatch.md` | config/prompt file | event-driven | No round/prompt file of any kind exists in this repo; no sibling kit directory exists to reference either |
| `prompts/delivery/HANDOFF.md` | config/contract doc | request-response | No `HANDOFF.md` exists in this repo at any path; only its section names are known from `REQUIREMENTS.md` prose |
| `PIPELINE.md` | manifest/config | transform | File confirmed absent by `find`; roadmap describes content that cannot be verified until supplied |
| `README.md` (front-door variant) | documentation/config | transform | The only tracked `README.md` is a different document (GSD handover README); the target file is confirmed absent |
| `prompts/documentation/HANDOFF.md` | config/contract doc | transform | File and its parent directory both confirmed absent by `find` |

**Recommendation to planner:** treat every file in this phase as build-from-requirements-text
(the verified quotes in `analysis/requirement-detail/PLAN100-10.md` and
`analysis/requirement-detail/NIGHT100-10.md`, plus the `[ASSUMED]` skeletons in
`01-RESEARCH.md`'s `## Code Examples`), not build-from-analog. For the three edit targets
(`PIPELINE.md`, `README.md`, `prompts/documentation/HANDOFF.md`), plans cannot be made fully
concrete until the user supplies these files per the Known Gap in `01-CONTEXT.md` — plan the
creation of the two new files (`D01-dispatch.md`, `HANDOFF.md`) as executable now, and gate the
three edits on file supply, re-locating the five-stage claim by content search rather than by the
roadmap's cited line numbers once each file lands.

## Metadata

**Analog search scope:** entire repository (`git ls-files`, `git status --porcelain -uall`,
recursive `find` for `PIPELINE.md`, `HANDOFF.md`, and any `prompts/` directory, all excluding
`.git/`).
**Files scanned:** 5 tracked files, 27 untracked planning/analysis files, repo root and full tree
depth for the three target filenames.
**Pattern extraction date:** 2026-09-28
**Tracked-source gate:** not applicable — no analog candidates of any kind were found (tracked or
gitignored-mirror), so no substitution was needed.
