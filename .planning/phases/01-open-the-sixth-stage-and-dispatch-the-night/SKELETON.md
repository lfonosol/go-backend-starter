# Walking Skeleton — harness-v1 (go-backend-starter)

**Phase:** 1
**Generated:** 2026-09-28

> **Domain note:** this project has no application code, framework, database, or deployment
> target in the conventional sense (confirmed absent by `01-RESEARCH.md` and `01-PATTERNS.md` —
> zero code analogs found anywhere in the repository). The "stack" here is a Markdown-based
> prompt-kit pipeline. Every row below is the domain-equivalent of the standard skeleton
> checklist, not a literal framework/DB/auth choice.

## Capability Proven End-to-End

> One sentence: the smallest user-visible capability that exercises the full stack.

"The practitioner can point at a real, git-committed sixth pipeline stage (`prompts/delivery/`)
whose handoff contract and manually-invoked dispatch round reference each other — the delivery
half of the pipeline exists as a real kit, not a plan for one."

## Architectural Decisions

| Decision | Choice | Rationale |
|---|---|---|
| Sixth-stage directory name | `prompts/delivery/` (locked, D-01) | Working name adopted by the planning session so the stage is one kit, not two; renaming after Phase 2 begins writing round files into it means renaming the directory plus 23 occurrences of the string across `REQUIREMENTS.md`/`PROJECT.md`/`STATE.md` — confirmed live by the user in `01-DISCUSSION-LOG.md`, one-way reversibility. |
| Round-file numbering scheme | `D01` (this phase) through `D06` (Phase 5), out of day-run order (accepted, D-02) | `D01`-`D03` were minted before `D04`-`D06`; renumbering into day-run order would churn every reference across the package for no functional gain. `D06` (reporting/handover) sits inside this kit because the register proposes no separate reporting kit. |
| Stage handoff contract shape | Per-stage `HANDOFF.md` with named, addressable sections — `Declared outputs` (verified sibling section name) and `Lessons` (verified sibling section name) | Matches the convention every existing kit in this package's own text uses (`prompts/documentation/HANDOFF.md`, `prompts/gsd-planning/HANDOFF.md`); later phases (`MORNING100-60`) append into `Declared outputs` by name, so the anchor must be stable from Phase 1 on. |
| Dispatch trigger mechanism | Manual round invocation by the practitioner at day's end, not a scheduled/cron job (D-04) | Success Criterion 3's own wording ("the practitioner runs one dispatch round... and leaves") and the requirement's source evidence ("when we close the computers at 5 o'clock in the evening...") both describe a deliberate end-of-day act. Decided under autopilot — flagged for the practitioner's review, not silently locked. |
| Execution substrate for overnight continuation | **Unresolved — open question** | No source in this package names what keeps the run alive after the practitioner's own machine goes offline at day's end. Flagged as a `<human-check>` in Plan 01-01 rather than guessed at. |

## Stack Touched in Phase 1

- [x] "Project scaffold" equivalent — `prompts/delivery/` directory created, plus a reusable
      `scripts/check-pipeline-stages.sh` content-search check script (this phase's Wave-0 gap
      closure, per `01-RESEARCH.md` "Wave 0 Gaps")
- [x] One real "write" — `prompts/delivery/HANDOFF.md`'s `Declared outputs` section, written by
      Plan 01-01
- [x] One real "read" wired to the write — `prompts/delivery/D01-dispatch.md`'s `Receives` line,
      which names `HANDOFF.md`'s `What this stage is handed` section as its source rather than
      restating the contract independently (the end-to-end wiring for this domain)
- [ ] "Deployment" equivalent — **BLOCKED.** The six-stage declaration in `PIPELINE.md`,
      `README.md` (front-door variant), and `prompts/documentation/HANDOFF.md` is gated on the
      user supplying those three files, which do not exist in this repository yet (`01-CONTEXT.md`
      Known Gap). Plan 01-02's tasks carry `<precondition>` guards for exactly this and remain
      incomplete until the files land.

## Out of Scope (Deferred to Later Slices)

- `NIGHT100-20` through `NIGHT100-50` — entering/bounding overnight mode, the verification loop,
  stop-on-broken-gate, and the automation boundary. These *append into* `D01-dispatch.md` later;
  Phase 1 leaves marked, empty insertion points and does not draft their content (per
  `01-RESEARCH.md`'s own anti-pattern warning).
- `D02-morning-review.md` (Phase 3), `D03-session-pack.md` (Phase 4), `D04-enter-overnight.md`
  (Phase 2), `D05-leave-overnight.md` (Phase 3), `D06-weekly-status.md` (Phase 5) — none of these
  five round files are created in this phase. The verified traceability map
  (`01-RESEARCH.md` § "Finding: D-02's 'D04 to D06'...") is the source of truth for which phase
  creates each one.
- The severity/criticality vocabulary (`I-030`, Decision 1) — Phase 2, reused by Phase 3.
- Resolving the execution-substrate open question — raised here, answered by whichever phase the
  practitioner's confirmation lands in.

## Subsequent Slice Plan

Each later phase adds one vertical slice on top of this skeleton without altering its
architectural decisions:

- Phase 2: entering/bounding the overnight run — `D04-enter-overnight.md`, the verification loop,
  stop-on-broken-gate, and the automation boundary appended into `D01-dispatch.md`.
- Phase 3: the morning opens on ranked decisions — `D02-morning-review.md`,
  `D05-leave-overnight.md`, criticality ranking.
- Phase 4: one generated pack for the daily session — `D03-session-pack.md`.
- Phase 5: the scope tracker and weekly report generated from the planning tool's own data —
  `D06-weekly-status.md`.
