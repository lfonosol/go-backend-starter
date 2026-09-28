# Requirements: harness-v1

**Defined:** 2026-09-20
**Core Value:** The harness runs a day's delivery without anyone present to press buttons, and the human's whole job in the morning is reading a ranked list of decisions that each carry a reason and a reversal.

## How to read this file

**Where the evidence lives.** Every citation in this file resolves inside the package. An `S-01`
timestamp is a moment in the working-session transcript under `workshop-docs/`; an `S-02` heading is
a dated section of `workshop-docs/practitioner-notes-2026-09-19.md`. **The register sheets and the
provenance notes do not travel** — they are working files on the way to a Google Sheet that becomes
the source of truth, so what each of them holds about a requirement travels on that requirement's
card under `analysis/requirement-detail/` instead: the quotation, the reasoning, the judgment calls,
the RAID links and the glossary terms. See *Pointers with no target inside the package*
in `ROADMAP.md`. Paths named as files a phase CREATES — `workbook/problems.csv`,
`workbook/review-findings.csv`, `workbook/signature-record.csv` — are paths in the repository the
receiving team builds in, not paths in this package.

**There are two identifier namespaces, and between them is a mapping rather than an equivalence.**

- **The change register owns `CR-xxx`** — the business's namespace, what was agreed, in the language
  of the approval. The change register mints `CR-010` to `CR-270`, flat and
  gapped by ten. **It does not move.**
- **This file, the roadmap and the requirement cards own family identifiers** — `CAPTURE100-10`,
  `NIGHT100-30`, `REPORT100-10` and the rest. This is the delivery namespace: what the handover site
  renders and what its navigation groups by. Its grammar is family code, group number, hyphen, item
  number, and `board/config.mjs` owns that grammar.

**One change record may become two delivery items, two may collapse into one, and either side can
change without renumbering the other.** For harness-v1 the mapping is one-to-one across 24 of the
register's 27 rows; `CR-250`, `CR-260` and `CR-270` are subtractions and take a delivery
identifier only when a roadmap phase adopts them. The relation is a mapping and a later round must
not read it as an identity.

**The mapping is written in both places, so a reader can go either way.** Every register row names
what it became, in its `Delivery ID` column. Every requirement below names the change record it came
from, on its own line. The two lists are the same 24 pairs, and each was written from one source in
one pass so they cannot disagree.

**Both namespaces are mint-once.** Gapped by ten, retired in place, never renumbered. The register
was renumbered flat four times (rounds 8 to 11, 19 and 20 September 2026) and each renumbering was
argued safe on the measured ground that nothing downstream cited the numbers yet. **That ground is
gone: the delivery namespace now cites every one of them.**

**Every row carries its `Type` and its source locus verbatim from the register.** `Change` means a
change to how the business works, awaiting the business's approval. `Rule` means a constraint that
qualifies the Change immediately above it. The locus is either an S-01 timestamp (the working
session transcript of 17 September 2026) or an S-02 heading (the practitioner's dictated notes of
19 September 2026). Both sources are tiered Authoritative.

**The quoted line under each requirement is the register's `Item` cell.** The reasoning behind each
row is in that row's `Note` cell, and it travels on the requirement's own card under
`analysis/requirement-detail/`, under *The reasoning on the register*; the judgment calls the
round-by-round provenance record holds travel there too, under *Judgment calls that bear on it*.
The provenance record itself is a working file and does not travel. **`ROADMAP.md` attaches the
evidence per phase to the requirements that phase covers, together with the source quotation
itself.**

**Section headings are the process stages of the decomposition record, in its order.** Seven of
the eight stages carry rows. `Testing and acceptance` carries none: its substance — a test document
short enough for a business tester who holds a day job — was absorbed into DEMO100-40 rather than
deleted, and its locus `S-01 40:54` stands on that row.

## v1 Requirements

All 24 register rows are v1. There is no deferred half.

### Workshop capture

- [ ] **CAPTURE100-10** — Feed the session live · `Change` · S-01 01:27:51 · change record `CR-010`
  > "Transcription feeds the planning tool during a session rather than after it, so planning and research begin while the session is still running."

  Feasibility is unestablished and is tracked as assumption **A-010** — the speaker says plainly
  *"I don't know if we can do that by that time"*. Creates the first round file and standing handoff
  under `prompts/workshop-prep/`.

### Requirements documentation

- [ ] **SITE100-10** — Generate the tracker · `Change` · S-01 01:16:04 · change record `CR-020`
  > "The scope tracker is generated from the planning tool's own phases and plans rather than assembled by hand."

  Replaces writing the tracker directly. Changes `prompts/documentation/P-GEN-07-scope-tracker.md`,
  `PIPELINE.md`, `board/csv-refresh.mjs`, `board/release.mjs` and `board/tracker-source.mjs`. One
  open question is carried to the practitioner: whether this row should also state an interactive
  round, or whether the tracker stays a whole carry of the planning tool's phases and plans. It was
  left silent because a selection over the tracker would break the traceability the tracker exists for.

- [ ] **SITE100-20** — Clean the content pages · `Change` · S-02 capture · change record `CR-030`
  > "Every content page on the handover site is reviewed and given an explicit organisation, page by page."

  The practitioner's declared first pass of this engagement, requested directly. The organisation
  decision per area is the output of this pass, not an input to it — tracked as issue **I-010**.
  Changes `board/config.mjs` NAV, `board/docs.mjs` and `board/editorial.mjs`.

- [ ] **SITE100-40** — Mark each content area · `Rule` · S-02 capture · change record `CR-050`
  > "Each content area is marked either as progressive-reveal or as human-facing, and that marking is recorded with the area."

  Decided during SITE100-20 and recorded by this row. It is what makes SITE100-30 buildable: without the
  marking the reveal has no input. Adds a marking field on each `NAV` and `ROADMAP_SECTIONS` entry in
  `board/config.mjs`, read by `board/docs.mjs`. Migrated from the prototype register when that sheet
  was dropped, no prototype having been reviewed on this engagement.

- [ ] **SITE100-30** — Add progressive reveal · `Change` · S-02 capture · change record `CR-040`
  > "The handover site gains progressive reveal, exposing the additional context made available to the model beneath what a human reader consumes."

  Depends on SITE100-40's marking and on SITE100-20's per-area decision. Changes `board/docs.mjs`,
  `board/detail.mjs`, `board/src/shell.html` and `board/src/chrome.css`.

- [ ] **KIT100-10** — Return the review's feedback · `Change` · S-02 where the harness ends · change record `CR-060`
  > "Feedback from a review meeting held after the workbook is signed re-enters the documentation stage as a source in its own right, and the registers and the tracker are corrected against it without renumbering."

  **The return path exists in no form.** The apply-changes round accepts only findings the kit's own
  validation rounds raised and signed. DEMO100-10 is the daily session and is not this — that session's
  feedback becomes delivery specifications inside the build loop and never reaches a register. The
  round it needs is undesigned. Risk **R-020** bears on it: the registers were assessed as useful at
  the first review and under-used afterwards. Creates
  `prompts/documentation/P-GEN-11-review-feedback.md` and `workbook/review-findings.csv`, reached by
  `P-GEN-06-apply-changes.md`.

- [ ] **KIT100-20** — Drop the signature record · `Change` · S-02 the signature apparatus · change record `CR-070`
  > "The documentation kit records no sheet signature: no round writes a digest-and-token row for a sheet, and no round gates on one. The repository's own history is what a later reader consults for what a sheet said and when, and the practitioner's acceptance of a sheet is recorded by the round that asked for it."

  Ruled out for the harness and not only for this engagement. Three grounds, in the practitioner's
  order: git already carries author, timestamp and full history, so the record is a hand-maintained
  weaker copy; the one thing git does not carry is approval as distinct from authorship, which is met
  by him saying yes in a recorded place; and the client-dispute ground does not survive contact,
  because a digest written by our own process and signed with a token our own agent typed is
  self-attested and is not evidence against a counterparty.

  **What must not go with it:** the handover boundary. A sheet the practitioner has accepted stops
  being a draft, and a later change goes through the apply-changes round. That is carried by an
  `Accepted:` line in the round's own provenance note and by the commit recording the act.
  **Out of this row's scope:** the per-finding `Signed` column, a different mechanism that gates
  `P-GEN-06-apply-changes.md`; removing it would remove that gate. Whether that column should exist
  at all is a separate question, carried to the practitioner as backlog item 63. **That backlog has
  no target inside this package** — it lives in the engagement repository's own build-state
  directory, which the package's export rules exclude by design. **The question is restated in full
  as Decision 4 in `ROADMAP.md`'s open-decisions appendix**, so a reader of this package can act on
  it without the backlog.

  **Scheduled for the hardening stage on the practitioner's own instruction.** Changes
  `prompts/documentation/HANDOFF.md`, `P-GEN-05-validate.md`, `P-GEN-07-scope-tracker.md`,
  `P-GEN-08-scope-tracker-validate.md`, `P-GEN-09-scope-tracker-merge.md`,
  `prompts/gsd-planning/HANDOFF.md`, `prompts/gsd-planning/P00-intake.md`, `CONTRACTS.md` section 7,
  `PIPELINE.md` stages 3 and 4, and three files under `board/test/`. No round then writes
  `workbook/signature-record.csv`, the lane file the record lived in, which this lane has never carried.

### Planning and roadmap

- [ ] **PLAN100-10** — Execute the agreed requirements · `Change` · S-02 where the harness ends · change record `CR-080`
  > "The signed requirements package is executed by the planning tool, so the harness continues past the published handover site into the delivery build rather than ending there."

  Closes the seam no row named. SITE100-10 carries the planning tool's output into the workbook; this row
  carries the same package on into build. NIGHT100-10 to NIGHT100-50 already hold what the run does — none of
  them states what the run is handed. **Creates the sixth-stage directory** and changes `PIPELINE.md`
  and `README.md`, which both declare five stages.

### Autonomous build

- [ ] **NIGHT100-10** — Dispatch at day's end · `Change` · S-01 25:16 · change record `CR-090`
  > "Work is dispatched at the end of the working day and runs unattended overnight, replacing a cycle bounded by working hours."

  The single largest win the delivery team named. Removes the need for someone to be present pressing
  buttons and keeping a machine awake. Creates `prompts/delivery/D01-dispatch.md` and
  `prompts/delivery/HANDOFF.md`, reached by `PIPELINE.md` and `README.md`.

- [ ] **NIGHT100-20** — Enter overnight mode · `Rule` · S-02 the mode transitions · change record `CR-100`
  > "Entering overnight mode is performed by an interactive round of its own, in which the practitioner selects what the night's run takes and the round then dispatches it."

  NIGHT100-10 states the rhythm and NIGHT100-30 to NIGHT100-50 state how the run behaves; none of them states what
  performs the transition into the mode, and the harness has no file that does. What the round asks,
  in what order and in what form is deliberately not stated — the practitioner set the implementation
  aside. Creates `prompts/delivery/D04-enter-overnight.md`.

- [ ] **NIGHT100-30** — Run the verification loop · `Rule` · S-02 how overnight mode terminates; S-01 25:42 · change record `CR-110`
  > "An unattended run is a verification loop: one agent runs the GSD automated process for a phase, a second agent checks that work, and the failures it finds are reassigned. The loop exits when everything passes, and is bounded either by five attempts or by only documentation or low-level issues remaining."

  The run terminates on a judgment about what is left, not on a tally of tries. Two bounds stand and
  either is sufficient. Both are stated values with no measurement behind them — assumption **A-020**.
  The second bound is not checkable without a severity classification the harness does not have —
  issue **I-030**, which the same vocabulary must serve for MORNING100-40. Both loci stand: S-02 carries the
  loop and the exit conditions, S-01 25:42 is the origin of the requirement that the run be bounded at
  all, and its count of three is superseded. Creates the verification-loop and exit-condition clauses
  in `prompts/delivery/D01-dispatch.md`.

- [ ] **NIGHT100-40** — Stop on a broken gate · `Rule` · S-01 25:45 · change record `CR-120`
  > "An unattended run that breaks a gate stops and waits, rather than working around the gate to keep going."

  A guardrail on NIGHT100-10, stated as its own rule. The morning then begins with a named failure rather
  than with a silent workaround to discover. Creates the stop-on-broken-gate clause in
  `prompts/delivery/D01-dispatch.md`.

- [ ] **NIGHT100-50** — Bound the automation · `Rule` · S-01 18:01 · change record `CR-130`
  > "The automation may move and transform data, write and change code, run tests, and prepare and propose work. A human approves, decides and releases."

  The automation boundary, permitted half and reserved half, in one row. It was written as two rows
  and the row carrying the reserved half was struck on review; a permission left by itself would tell
  the business what the automation may do and nothing about what it may not, so both clauses are
  folded here. Creates the automation boundary in `prompts/delivery/D01-dispatch.md`.

### Morning review

- [ ] **MORNING100-10** — Open with the decisions · `Change` · S-01 26:48 · change record `CR-140`
  > "The working day opens with a review of the decisions the overnight run inferred, replacing an unguided read of what changed."

  Already built and in use by the practitioner; proposed here as a harness capability for the team.
  Its value was described as telling you where to dig, rather than making you dig. Creates
  `prompts/delivery/D02-morning-review.md`.

- [ ] **MORNING100-20** — Leave the run for morning mode · `Rule` · S-02 the mode transitions · change record `CR-150`
  > "Leaving the overnight run and entering morning mode is performed by an interactive round of its own, in which the run is closed and the practitioner selects what the morning takes from it."

  MORNING100-10 states that the day opens with the review and MORNING100-30 is the record that review reads.
  Neither closes the run, and the harness has no file that does. It sits in Morning review rather
  than in Autonomous build because the mode it enters is the morning one. Creates
  `prompts/delivery/D05-leave-overnight.md`.

- [ ] **MORNING100-30** — Log every inference · `Rule` · S-01 26:15 · change record `CR-160`
  > "An unattended run logs every decision it inferred, or would have asked about, with the reason it chose as it did and how to reverse it."

  The record MORNING100-10 reads. Reason and reversal are both required: a decision without its reversal is
  a decision the reviewer cannot act on. Creates the decision log that
  `prompts/delivery/D01-dispatch.md` writes and `prompts/delivery/D02-morning-review.md` reads.

- [ ] **MORNING100-40** — Rank by criticality · `Rule` · S-01 26:57 · change record `CR-170`
  > "Entries in the morning review are classified by criticality and the highest-value ones are read first."

  Proposed as the answer to review volume. The underlying constraint is stated plainly in the
  session and is risk **R-010**: the bigger the work pushed to the model, the more the human becomes
  the bottleneck. Needs the same severity vocabulary as NIGHT100-30 — issue **I-030**, one classification
  serving both. Creates the criticality ordering in `prompts/delivery/D02-morning-review.md`.

- [ ] **MORNING100-50** — Capture the lessons · `Rule` · S-01 41:53 · change record `CR-180`
  > "The morning review ends with a lessons-learned step whose agreed output is written into the repository, and which may be promoted from this engagement to the harness itself."

  The promotion path is explicit and is what makes the harness improve across engagements rather than
  within one. A lesson stays with the project unless it is promoted. Changes `PIPELINE.md`,
  `prompts/documentation/HANDOFF.md` section Lessons and `prompts/gsd-planning/HANDOFF.md` section
  Lessons.

- [ ] **MORNING100-60** — Log the problems · `Rule` · S-01 40:03 · change record `CR-190`
  > "Problems encountered are logged systematically as they occur, for use during the engagement and at its retrospective."

  Requested directly, with the reason: the team had been relying on memory to recall pain points at
  retrospectives. Creates `workbook/problems.csv`, reached by `workbook/README.md` and
  `prompts/delivery/HANDOFF.md` section Declared outputs.

### Daily demo and feedback

- [ ] **DEMO100-10** — Generate the session pack · `Change` · S-02 the daily session pack; S-01 37:58 · change record `CR-200`
  > "The daily session's materials are generated from the planning data as one pack, built by an interactive round in which the practitioner selects what the pack contains, rather than written by hand."

  Replaces the agenda-only row the sheet carried: the pack is the deliverable and the agenda alone
  was never it. **The build mechanism is a prompt and not a batch script**, because the round must ask
  which features are worth demonstrating, what to propose next and what a tester should try, and the
  planning data holds none of the three. Creates `prompts/delivery/D03-session-pack.md` as an
  interactive round.

- [ ] **DEMO100-20** — Demonstrate the overnight build · `Rule` · S-02 the daily session pack; S-01 30:30 · change record `CR-210`
  > "The pack carries a demonstration of what the overnight run built."

  One of three parts of DEMO100-10. The features worth showing are chosen during the interactive round,
  because the planning data records what was built and not what is worth demonstrating. Its input is
  the output of NIGHT100-10. Creates the demonstration section of `prompts/delivery/D03-session-pack.md`.

- [ ] **DEMO100-30** — Propose what comes next · `Rule` · S-02 the daily session pack; S-01 30:30 · change record `CR-220`
  > "The pack carries what is proposed next, and the session's agreement becomes the next run's specifications."

  The half that closes the delivery loop: the agreement reached in the session is the input PLAN100-10
  hands the next unattended run. It is **not** the post-signature return path — KIT100-10 is that, and
  it re-enters the registers instead of the build. Creates the proposal section of
  `prompts/delivery/D03-session-pack.md` and the specification handoff it writes for
  `prompts/delivery/D01-dispatch.md`.

- [ ] **DEMO100-40** — Hand over for UAT · `Rule` · S-02 the daily session pack; S-01 40:54 · change record `CR-230`
  > "The pack carries a UAT handover for what was built, short enough for a business tester who holds a day job to act on."

  The part no row carried before: the register held the demonstration and the planning of what comes
  next, and separately a rule about the size of a test document, but nothing said the session hands
  the business something to test with. A test document that is expensive to read is a feature that
  does not get tested. Dependency **D-010** is its precondition: the client's testers must give time
  alongside their day jobs, for every delivered feature, at the pace this harness sets. Creates the
  UAT-handover section of `prompts/delivery/D03-session-pack.md`.

### Reporting and handover

- [ ] **REPORT100-10** — Generate the weekly status report · `Change` · S-01 36:27; S-02 the mode transitions · change record `CR-240`
  > "Status reporting is generated weekly from the planning tool against a fixed template, by an interactive round in which the practitioner selects what the report contains, replacing hand-written updates."

  The stated cause is pace: with delivery this fast, hand-written reporting becomes the bottleneck.
  The planning tool already holds the phases, milestones and roadmap the report needs. **The cadence
  is weekly and the practitioner named it so** in order to separate it from the daily meeting: *"let
  us call it the weekly status report, because we have the daily meeting"*. DEMO100-10 is the daily
  artifact and this is the weekly one; they share neither rhythm nor mechanism. Creates
  `scripts/status-report.mjs` and its template, and `prompts/delivery/D06-weekly-status.md` as the
  interactive round that selects the contents and runs the generator.

## v2 Requirements

None. The register carries no deferred half: the practitioner's scope test of 2026-09-20 either kept
a row or struck it.

## Out of Scope

Two kinds of exclusion, excluded for different reasons. The first group is recorded `In` on the
scope-decision record and carries no register row — struck by the practitioner's own scope
test of 2026-09-20, *does this cause a file in this repository to change, be deleted, or be created?*,
which cut the register from 78 rows to 24. The second group is recorded `Out` at the source.

| Feature | Reason |
|---------|--------|
| LLM-first design — every capability behind an API and an MCP layer | A design principle applied inside each phase, not build work of its own. No register row |
| Daily vertical slices, one or more features delivered and testable per day | The delivery rhythm the harness runs at. No register row |
| Repository structure and a per-area agent as the control on reviewer effort | Existing practice, already in the tree. No register row |
| Architecture quality checks layered on the structure | Depends on a technique owned by an external party; no adoption decision has been taken |
| Accuracy measured against a golden data set agreed before the pipeline runs | A measurement practice, not a harness file change. No register row |
| Phases and steps constrained to isolated parts of the architecture | A direction given to the planning tool. No register row |
| A roadmap step classifying each item as an application or an MCP command | Proposed in the session; no register row |
| Self-diagnosis — the agent reports what it did and why at the end of a task | Proposed in the session; no register row |
| Chat bots tied to the agentic work | Proposed in the session's second half and read in scope under the reading rule; no register row |
| Role-based views beyond the client view | Stated as the eventual destination. The near-term scope is the client view plus progressive reveal, which SITE100-20 to SITE100-40 carry |
| The next client engagement's own project scope | Assigned to client preparation by the reading rule, not to harness requirements |
| Client engagement logistics — travel, rooms, system access, account provisioning, creating the shared chat channel | Operational preparation for a different engagement. No harness capability is stated for any of it. Note the near miss: the chat **bots** are in scope, creating the **channel** is not |
| The prior engagement's retrospective outcomes and maintenance handover | Closed before the session. The source of the lessons this work answers, not work this engagement performs |
| The prior engagement's domain content | Used in the session only as worked examples. Kept in the glossary so a reader can follow them; never a harness requirement |
| An external party's measurement technique | Named as a candidate to evaluate, not as something this engagement builds |

## Open items carried from the RAID register

Seven rows stand on the RAID register, and all seven are given in full below. `Owner` is empty on every one of them by decision — an
owner is assigned at the review meeting the practitioner holds after reading the sheet. `I-020` is
retired in place and its number is never reused, so the Issue block reads `I-010` then `I-030` with
a declared hole between them.

**Every one of the seven is attached to the phase it bites, in `ROADMAP.md`**, rather than left in
a sheet nobody re-reads: `R-010` → Phase 3; `R-020` → Phase 7; `A-010` → Phase 7; `A-020` → Phase 2;
`I-010` → Phase 6; `I-030` → Phases 2 and 3; `D-010` → Phase 4.

**The `Bears on` column names the delivery identifier; the RAID sheet itself names the change
record.** The RAID register is unchanged — it cites the change register, and the change register has
not moved. Both columns are given below, so crossing between the two namespaces needs no third
document.

| ID | Type | Item | Bears on (delivery) | As the RAID sheet cites it |
|---|---|---|---|---|
| R-010 | Risk | The human reviewer becomes the bottleneck: the more work pushed to the model, the more there is for one person to read and approve | MORNING100-40 | `CR-170` |
| R-020 | Risk | The registers go stale after the initial review. The change register was assessed as useful at the first client review and under-used afterwards, and the RAID register as not chased to the end | KIT100-10 | `CR-060` |
| A-010 | Assumption | Transcription can feed the planning tool during a session in the time available. The speaker states he does not know whether it can be done by then | CAPTURE100-10 | `CR-010` |
| A-020 | Assumption | Five attempts, or a remainder of documentation and low-level issues only, is a sufficient bound on an unattended verification loop. Both are stated values and no measurement supports either | NIGHT100-30 | `CR-110` |
| I-010 | Issue | Which content areas take progressive reveal and which are human-facing is not yet decided. The decision is the output of the content clean-up pass, not an input to it | SITE100-20, SITE100-30, SITE100-40 | `CR-030`, `CR-040`, `CR-050` |
| I-030 | Issue | No severity classification exists that an unattended run can apply to its own findings, and none exists for the morning review to rank by. Whether one vocabulary serves both, and what its levels are, is undecided | NIGHT100-30, MORNING100-40 | `CR-110`, `CR-170` |
| D-010 | Dependency | The client's testers must give time alongside their day jobs, for every delivered feature, for business testing to happen at the delivery pace this harness sets | DEMO100-40 | `CR-230` |

**One risk is live, uncited, and deliberately not on this sheet.** The practitioner raised it while
the engagement was being set up: **every requirement in the transcript changes the harness that is
shown to clients, and the harness is being used to change itself.** The RAID round judged it a real
risk that belongs on the sheet and did not mint it, for a stated reason — it was said to an agent in
conversation and appears in neither source, and writing it would have put an uncited row on a sheet
whose value is that every row can be checked against something. The trigger has fired five times
(rounds 6, 8, 9, 10 and 11), each time re-measured with a control term in the same run, and each
time found unmet. **It is minted as `R-080` at the first round after the concern appears in a
source** — one appended dated heading in the practitioner's notes closes it. It bears on all eight
phases and is carried as **Decision 5 in `ROADMAP.md`'s open-decisions appendix**, which is its only
home in this package.

## Traceability

Which phases cover which requirements. Populated during roadmap creation.

| Requirement | Change record | Phase | Status |
|-------------|---------------|-------|--------|
| CAPTURE100-10 | `CR-010` | Phase 7 | Pending |
| SITE100-10 | `CR-020` | Phase 5 | Pending |
| SITE100-20 | `CR-030` | Phase 6 | Pending |
| SITE100-30 | `CR-040` | Phase 6 | Pending |
| SITE100-40 | `CR-050` | Phase 6 | Pending |
| KIT100-10 | `CR-060` | Phase 7 | Pending |
| KIT100-20 | `CR-070` | Phase 8 | Pending |
| PLAN100-10 | `CR-080` | Phase 1 | Pending |
| NIGHT100-10 | `CR-090` | Phase 1 | Pending |
| NIGHT100-20 | `CR-100` | Phase 2 | Pending |
| NIGHT100-30 | `CR-110` | Phase 2 | Pending |
| NIGHT100-40 | `CR-120` | Phase 2 | Pending |
| NIGHT100-50 | `CR-130` | Phase 2 | Pending |
| MORNING100-10 | `CR-140` | Phase 3 | Pending |
| MORNING100-20 | `CR-150` | Phase 3 | Pending |
| MORNING100-30 | `CR-160` | Phase 3 | Pending |
| MORNING100-40 | `CR-170` | Phase 3 | Pending |
| MORNING100-50 | `CR-180` | Phase 3 | Pending |
| MORNING100-60 | `CR-190` | Phase 3 | Pending |
| DEMO100-10 | `CR-200` | Phase 4 | Pending |
| DEMO100-20 | `CR-210` | Phase 4 | Pending |
| DEMO100-30 | `CR-220` | Phase 4 | Pending |
| DEMO100-40 | `CR-230` | Phase 4 | Pending |
| REPORT100-10 | `CR-240` | Phase 5 | Pending |

**Coverage:**
- v1 requirements: 24 total
- Mapped to phases: 24
- Unmapped: 0

---
*Requirements defined: 2026-09-20*
*Last updated: 2026-09-20 after initial definition*
