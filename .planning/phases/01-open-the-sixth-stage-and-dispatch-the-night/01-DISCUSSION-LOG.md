# Phase 1: Open the sixth stage and dispatch the night - Discussion Log

> **Audit trail only.** Do not use as input to planning, research, or execution agents.
> Decisions are captured in CONTEXT.md — this log preserves the alternatives considered.

**Date:** 2026-09-28
**Phase:** 1-Open the sixth stage and dispatch the night
**Areas discussed:** Sixth-stage directory name (Decision 2), Risk R-080 (Decision 5), Dispatch trigger mechanism, Delivery stage's HANDOFF.md format

---

## Sixth-stage directory name (Decision 2)

| Option | Description | Selected |
|--------|-------------|----------|
| Keep `prompts/delivery/` | Already the working name; renaming after Phase 2 writes into it gets progressively more expensive | ✓ |
| Rename to `prompts/execution/` | The other name two prior analyses used | |

**User's choice:** Keep `prompts/delivery/` (Recommended)
**Notes:** User confirmed live via interactive question during this session.

| Option | Description | Selected |
|--------|-------------|----------|
| Accept both consequences as-is | Round files D04-D06 out of day-order; D06 reporting round inside delivery kit | ✓ |
| Change the round numbering | Renumber D01-D06 into day-run order | |
| Change where D06 lives | Give reporting/handover its own kit | |

**User's choice:** Accept both consequences as-is (Recommended)
**Notes:** User confirmed live via interactive question during this session.

---

## Risk R-080 — the harness changing itself (Decision 5)

| Option | Description | Selected |
|--------|-------------|----------|
| Mint R-080 now as a locked decision, all-phases | Formally record the recurring, previously-unminted risk | ✓ |
| Leave it unminted for now | Proceed without resolving it | |
| Review full RAID reasoning first | Defer the decision | |

**User's choice:** Mint R-080 now as a locked decision, applying to all phases (Recommended)
**Notes:** Confirmed live via interactive question, prior to discuss-phase starting. During
discuss-phase, a nuance was discovered: the roadmap's own closure text for Decision 5 requires a
further external step — the practitioner appending a new dated heading to the external
`workshop-docs/` practitioner notes — to formally mint `R-080` on the RAID sheet. This CONTEXT.md
decision records the user's confirmation for this package's planning purposes; the external
append step remains outstanding and is the user's to complete.

---

## Dispatch trigger mechanism

| Option | Description | Selected |
|--------|-------------|----------|
| A command the practitioner runs manually at day's end | Matches "the practitioner runs one dispatch round... and leaves" (Success Criterion 3) | ✓ |
| A scheduled/cron job, no manual step | Fires automatically at a fixed time | |
| Something else | User-described alternative | |

**User's choice:** Not answered live — user was unavailable at this point in the session
(autopilot mode). Decided by the agent based on Success Criterion 3's explicit wording and the
requirement card's source evidence quote ("when we close the computers at 5 o'clock in the
evening, we want things to happen").
**Notes:** Flagged in CONTEXT.md as an autopilot assumption for the user to review, not silently
locked.

---

## Delivery stage's HANDOFF.md format

**User's choice:** Not discussed as a direct question — resolved as the agent's Discretion (see
below), since the user was unavailable at this point in the session (autopilot mode).
**Notes:** Follows the same convention as sibling stage handoffs already established elsewhere in
the pipeline, per the canonical refs in CONTEXT.md.

---

## the agent's Discretion

- **Dispatch trigger mechanism** — decided under autopilot in the user's absence; grounded in
  Success Criterion 3's explicit wording, but flagged in CONTEXT.md for the user to review rather
  than treated as silently locked.
- **Delivery stage's `HANDOFF.md` format** — left to the planner/executor to follow the
  established sibling-stage convention rather than prescribing exact prose.

## Deferred Ideas

None — discussion stayed within phase scope.
