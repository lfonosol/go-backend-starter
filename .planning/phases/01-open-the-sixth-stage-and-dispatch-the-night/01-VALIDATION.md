---
phase: "01"
slug: "open-the-sixth-stage-and-dispatch-the-night"
status: draft
nyquist_compliant: true
wave_0_complete: false
created: "2026-09-28"
---

# Phase 01 — Validation Strategy

> Per-phase validation contract for feedback sampling during execution.

---

## Test Infrastructure

| Property | Value |
|----------|-------|
| **Framework** | none — shell-based file-existence/content assertions (`test -f`, `grep -q`); no code, no test framework in this repo |
| **Config file** | none — see Wave 0 |
| **Quick run command** | `test -d prompts/delivery && test -f prompts/delivery/D01-dispatch.md && test -f prompts/delivery/HANDOFF.md` |
| **Full suite command** | run every `<automated>` command across `01-01-PLAN.md` and `01-02-PLAN.md` in sequence as one shell script |
| **Estimated runtime** | ~2 seconds (file/grep checks only, no build or test-runner startup cost) |

---

## Sampling Rate

- **After every task commit:** Run the quick run command above (file existence).
- **After every plan wave:** Run the full suite command (all `<automated>` checks for the wave's plan).
- **Before `/gsd-verify-work`:** Full suite must be green, plus a human confirms the `PIPELINE.md`/`README.md` wording reads correctly — this is prose, not logic, so a human read is the real gate for Plan 01-02.
- **Max feedback latency:** 5 seconds (shell assertions only; no compilation or network I/O).

---

## Per-Task Verification Map

| Task ID | Plan | Wave | Requirement | Threat Ref | Secure Behavior | Test Type | Automated Command | File Exists | Status |
|---------|------|------|-------------|------------|-----------------|-----------|-------------------|-------------|--------|
| 01-01-T1 | 01-01 | 1 | PLAN100-10, NIGHT100-10 | V5 (prompt-injection surface) | `D01-dispatch.md` names only practitioner-controlled instructions, no unreviewed external text | smoke | `test -d prompts/delivery && [ "$(ls -1 prompts/delivery \| wc -l)" -eq 2 ] && test -f prompts/delivery/HANDOFF.md && test -f prompts/delivery/D01-dispatch.md && grep -qi "declared outputs" prompts/delivery/HANDOFF.md && grep -qi "what this stage is handed" prompts/delivery/HANDOFF.md && grep -q "HANDOFF.md" prompts/delivery/D01-dispatch.md && grep -qi "practitioner" prompts/delivery/D01-dispatch.md && ! grep -Eqi "cron\|scheduled job" prompts/delivery/D01-dispatch.md` | ✅ (creates the dir/files) | ⬜ pending |
| 01-01-T2 | 01-01 | 1 | NIGHT100-10 | — | D06/reporting-round placement and day's-end trigger wording present, directory stays at exactly 2 files | smoke | `grep -q "5 o'clock" prompts/delivery/D01-dispatch.md && grep -q "D06" prompts/delivery/D01-dispatch.md && grep -qi "lessons" prompts/delivery/HANDOFF.md && [ "$(ls -1 prompts/delivery \| wc -l)" -eq 2 ]` | ✅ | ⬜ pending |
| 01-01-T3 | 01-01 | 1 | PLAN100-10 | — | `check-pipeline-stages.sh` correctly discriminates five-stage vs six-stage vs missing-file content; R-080 and the freeze-brake are named in the handoff | smoke | `test -x scripts/check-pipeline-stages.sh && grep -qi "lessons" prompts/delivery/HANDOFF.md && grep -q "R-080" prompts/delivery/HANDOFF.md && grep -q "handover-freeze" prompts/delivery/HANDOFF.md && echo "the pipeline has five stages, ending at the handover site." > /tmp/gsd-stage-check-old.md && ! bash scripts/check-pipeline-stages.sh /tmp/gsd-stage-check-old.md && echo "the pipeline has six stages, the sixth being prompts/delivery/." > /tmp/gsd-stage-check-new.md && bash scripts/check-pipeline-stages.sh /tmp/gsd-stage-check-new.md && ! bash scripts/check-pipeline-stages.sh /tmp/gsd-stage-check-missing.md` | ✅ (creates the script) | ⬜ pending |
| 01-02-T1 | 01-02 | 2 | PLAN100-10 | — | `PIPELINE.md` declares six stages and names `prompts/delivery` | smoke | `test -f PIPELINE.md && bash scripts/check-pipeline-stages.sh PIPELINE.md && grep -q "prompts/delivery" PIPELINE.md` | ❌ Wave 0 — blocked on user supplying `PIPELINE.md` | ⬜ pending |
| 01-02-T2 | 01-02 | 2 | PLAN100-10 | — | Front-door `README.md` declares six stages, zero "five stages" occurrences remain, names `prompts/delivery` | smoke | `test -f README.md && bash scripts/check-pipeline-stages.sh README.md && grep -q "prompts/delivery" README.md && [ "$(grep -oi "five stages" README.md \| wc -l)" -eq 0 ]` | ❌ Wave 0 — blocked on user supplying the real front-door `README.md` (the GSD handover `README.md` currently at repo root is not this file) | ⬜ pending |
| 01-02-T3 | 01-02 | 2 | PLAN100-10, NIGHT100-10 | — | `prompts/documentation/HANDOFF.md` declares six stages and names `prompts/delivery` | smoke | `test -f prompts/documentation/HANDOFF.md && bash scripts/check-pipeline-stages.sh prompts/documentation/HANDOFF.md && grep -q "prompts/delivery" prompts/documentation/HANDOFF.md` | ❌ Wave 0 — blocked on user supplying `prompts/documentation/HANDOFF.md` | ⬜ pending |
| — | — | — | NIGHT100-10 | — | Overnight-unattended behavior actually survives the practitioner leaving | manual-only | — cannot be automated until Open Question 1 (execution substrate) is resolved | ❌ manual-only, justified: no execution substrate is defined yet, so there is nothing to script against | ⬜ pending |

*Status: ⬜ pending · ✅ green · ❌ red · ⚠️ flaky*

---

## Wave 0 Requirements

- [ ] `prompts/delivery/` directory, `D01-dispatch.md`, `HANDOFF.md` — created by Plan 01-01 itself (not a pre-existing gap; listed here because the verification map's "File Exists" column reports them as not-yet-existing before Plan 01-01 runs).
- [ ] `scripts/check-pipeline-stages.sh` — created by Plan 01-01 Task 3; Plan 01-02's three tasks depend on it existing and being executable.
- [ ] `PIPELINE.md`, real front-door `README.md`, `prompts/documentation/HANDOFF.md` — **user-supplied, external to this phase's own tasks.** These block Plan 01-02's three edit tasks entirely until supplied (per `01-CONTEXT.md`'s "Known gap" and the `<precondition>` gates already written into `01-02-PLAN.md`).

---

## Manual-Only Verifications

| Behavior | Requirement | Why Manual | Test Instructions |
|----------|-------------|------------|--------------------|
| Overnight-unattended dispatch survives the practitioner closing their laptop and leaving | NIGHT100-10 | No execution substrate is defined yet (RESEARCH.md Open Question 1) — there is nothing to script against until that's resolved | Once an execution substrate is chosen: run the dispatch round, close the initiating machine, and confirm the run is still progressing/completed after the machine is gone |
| `PIPELINE.md`/`README.md` six-stage wording reads correctly as prose | PLAN100-10 | This is a prose-quality judgment, not a logic check the grep-based smoke tests can make | After Plan 01-02 runs, a human reads the edited sections in context and confirms the wording is not just technically six-stage-compliant but reads naturally |

---

## Validation Sign-Off

- [x] All tasks have `<automated>` verify or Wave 0 dependencies
- [x] Sampling continuity: no 3 consecutive tasks without automated verify
- [x] Wave 0 covers all MISSING references (the three user-supplied files, named above)
- [x] No watch-mode flags
- [x] Feedback latency < 5s
- [x] `nyquist_compliant: true` set in frontmatter

**Approval:** pending
