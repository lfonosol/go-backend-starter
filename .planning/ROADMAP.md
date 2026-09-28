# Roadmap: harness-v1

**Created:** 2026-09-20 · **Enriched:** 2026-09-20
**Phases:** 8 · **Requirements mapped:** 24 of 24 ✓
**Structure:** Dependency order. The delivery half has a single root and runs first; the
board-side work depends on nothing and follows.

## Contents

- [How this roadmap is ordered](#how-this-roadmap-is-ordered)
- [How to read a phase entry](#how-to-read-a-phase-entry)
- [Where the evidence lives](#where-the-evidence-lives)
- [Phases](#phases)
  - [Phase 1 · Open the sixth stage and dispatch the night](#phase-1-open-the-sixth-stage-and-dispatch-the-night)
  - [Phase 2 · A night that bounds itself](#phase-2-a-night-that-bounds-itself)
  - [Phase 3 · The morning opens on ranked decisions](#phase-3-the-morning-opens-on-ranked-decisions)
  - [Phase 4 · One pack for the daily session](#phase-4-one-pack-for-the-daily-session)
  - [Phase 5 · Generated, not hand-assembled](#phase-5-generated-not-hand-assembled)
  - [Phase 6 · The handover site says what each area is for](#phase-6-the-handover-site-says-what-each-area-is-for)
  - [Phase 7 · Close the two open return paths](#phase-7-close-the-two-open-return-paths)
  - [Phase 8 · Hardening — the signature apparatus leaves the kit](#phase-8-hardening--the-signature-apparatus-leaves-the-kit)
- [Appendix](#appendix)
  - [Open decisions](#open-decisions)
  - [Decisions taken during planning, and where each one lives](#decisions-taken-during-planning-and-where-each-one-lives)
  - [External preconditions](#external-preconditions)
  - [Assumptions](#assumptions)
  - [Glossary terms in play](#glossary-terms-in-play)
  - [Pointers with no target inside the package](#pointers-with-no-target-inside-the-package)
  - [Coverage](#coverage)
- [Progress](#progress)

## Overview

harness-v1 extends the pod's five-stage pipeline into a delivery loop. The journey runs in
dependency order, because the delivery half has a single root: a sixth pipeline stage must exist
before any round can write a clause into a file inside it. So the roadmap opens the stage and
dispatches a night (Phase 1), bounds what that night may do (Phase 2), opens the morning on a
ranked review of what it inferred (Phase 3), and turns the day's session into one generated pack
whose agreement becomes the next night's specifications (Phase 4) — at which point the loop is
closed and each turn of it is visible. The remaining work depends on nothing in that half and
follows: the two hand-assembled artifacts become generated ones (Phase 5), the handover site's
content areas gain an explicit organisation and progressive reveal (Phase 6), and the two open
return paths into the requirements record are designed (Phase 7). Hardening is last: the signature
apparatus leaves the kit (Phase 8).

Every phase states its outcome as something a reader can see. Where dependency order and visible
value pulled against each other, dependency order decided the ordering and the phase goal was
written so the visible outcome is plain.

## How this roadmap is ordered

**The delivery half has a root and the board-side half does not.** Phase 1 creates the sixth-stage
directory. Five rules in Phase 2, six in Phase 3 and four in Phase 4 all write clauses into files
inside that directory, so none of them can land before it exists. Phases 5, 6 and 7 touch the
board, the prompt kits and the documentation stage, and depend on nothing in the delivery half —
Phase 5's weekly-report half is the single exception, and it is why that phase depends on Phase 1.

**Phase 8 is last by instruction, not by dependency.** No phase produces an input to it. The
practitioner scheduled the signature removal for the hardening stage in his own words, and the
sequencing honours that.

**There are two identifier namespaces and a mapping between them.** The change register owns
`CR-010` to `CR-270` — the business's namespace, what was agreed, in the language of the approval,
and it does not move. This roadmap and the requirement cards own family identifiers —
`CAPTURE100-10`, `NIGHT100-30`, `REPORT100-10` and the rest — which is the delivery namespace the
handover site renders and its navigation groups by. **Between them is a mapping, not an
equivalence:** one change record may become two delivery items, two may collapse into one, and
either side can change without renumbering the other. For harness-v1 the mapping is one-to-one
across 24 of the register's 27 rows — the three subtractions `CR-250`, `CR-260` and `CR-270` take
a delivery identifier only when a phase adopts them — and it is written in both directions, in the
register's own `Delivery ID` column and the change-record column in `REQUIREMENTS.md`, so a reader
can start from either.

**Both namespaces are mint-once**, gapped by ten, retired in place, never renumbered. The register
was renumbered flat four times during rounds 8 to 11, and each renumbering was argued safe on the
measured ground that nothing downstream cited the numbers yet. **That ground is gone: the delivery
namespace now cites every one of them.**

## How to read a phase entry

Two readers, one document, at two depths.

**The human reads the top of each entry** — the Goal, the Mode, the requirements it carries, and
the Success Criteria, which state what must be TRUE when the phase is done. Nothing below that
line is needed to understand what the phase delivers.

**The agent that builds the phase reads the bands underneath**, and they are there so a judgment
call can be settled mid-build instead of re-opened:

| Band | What it holds |
|---|---|
| **Decides** | An open decision this phase must close. Not a remark — an item. Every one of them is repeated in the [Open decisions](#open-decisions) appendix with its blast radius |
| **Preconditions** | Outside work that holds the phase closed until it is done. Not a requirement: a permission, a check, or a grant |
| **Assumptions this phase rests on** | A load-bearing guess, with what follows if it is wrong |
| **Notes for planning** | What the phase depends on, its plan count, and everything else a planner needs and would otherwise rediscover |

**The per-requirement evidence is on the requirement card, not here.** One card per requirement
under `analysis/requirement-detail/`, keyed by the same identifier the `Requirements:` line
names. Each card carries a section headed `## The evidence`: the sentence someone actually said
with its locus, the reasoning the register's own `Note` cell carries, the judgment calls the
provenance notes record against that row, the RAID rows linked to it, and the glossary terms in
play. The phase-level bands above stay whole-phase; a fact about one requirement lives on that
requirement's card.

**The evidence is quoted, not paraphrased.** A source quotation is the speaker's own words as the
transcript renders them. Where the transcript's speech-to-text mis-captured a word, the correction
is labelled in square brackets and is a one-step inference of the same kind the glossary records —
never a silent repair.

**Speakers are named by role.** The practitioner is the person whose dictated notes are the second
source; the delivery lead and the delivery-team participants are the other voices in the working
session. Every quotation carries its locus, so attribution can be checked at the source.

## Where the evidence lives

**Inside the package, beside this file.** A citation nobody can follow is a citation that has to be
believed, so the handover carries its own evidence.

| Citation shape | Where the package carries it |
|---|---|
| `S-01 <timestamp>` | `workshop-docs/` — the working-session transcript of 17 September 2026, 93 minutes, five speakers, 1,242 lines. Read it at `workshop-docs/Apax-Solita-WGSN-Working--5bbf25a2-51c5-4dee-8682-655f8f5d9da7-2026-09-17-13-30-00.md`, which carries every line under the locus the citation names; deep-link a moment by appending `?t=<seconds>` to the meeting address at the head of that page |
| `S-02 <heading>` | `workshop-docs/practitioner-notes-2026-09-19.md` — the practitioner's own dictated notes, under the dated heading the locus names |
| A register row's `Item`, `Note` and `Source` | The requirement's own card under `analysis/requirement-detail/` — the `Item` as the quotation at the head of the card, the `Note` under *The reasoning on the register*, and the `Source` on the card's `Sources:` line |
| A RAID row | The card of every requirement the row attaches to, under *RAID rows linked to it*, and the seven-row summary in `REQUIREMENTS.md` § *Open items carried from the RAID register* |
| A canonical term | The card's *Glossary terms in play*, and [Glossary terms in play](#glossary-terms-in-play) below |
| A judgment call, or a struck row and why it was struck | The card's *Judgment calls that bear on it* |
| A scope decision | Out of Scope, in `PROJECT.md` and in `REQUIREMENTS.md` |
| A process stage | `REQUIREMENTS.md`'s section headings, which are the decomposition's stages in its order |

**`workshop-docs/` is published on the site and is not in the downloadable archive, and the register sheets do not travel at all.** The change register,
the RAID sheet, the glossary, the scope-decision record, the decomposition and the four provenance
notes stay in the engagement's own working lane: they are intermediate working files on the way to a
Google Sheet that becomes the source of truth for the values people edit, and a copy of a working
file inside a handover goes stale the day it ships. **What each of them holds about a requirement
travels on that requirement's card instead**, which is what the table above points at. The position
is stated in
[Pointers with no target inside the package](#pointers-with-no-target-inside-the-package) rather
than left to be discovered.

**Where a pointer names a file a phase CREATES, it is not a dangling pointer and it stays.**
`workbook/problems.csv` (Phase 3) and `workbook/review-findings.csv` (Phase 7) are paths in the
repository the receiving team builds in, not paths in this package.

---

## Phases

**Phase Numbering:**
- Integer phases (1, 2, 3): Planned milestone work
- Decimal phases (2.1, 2.2): Urgent insertions (marked with INSERTED)

Decimal phases appear between their surrounding integers in numeric order.

- [ ] **Phase 1: Open the sixth stage and dispatch the night** - The pipeline continues past the published handover site, and a day's work is dispatched to run unattended
- [ ] **Phase 2: A night that bounds itself** - The unattended run is entered deliberately, verifies its own work, stops on a broken gate, and states what it may not do
- [ ] **Phase 3: The morning opens on ranked decisions** - The run is closed by a round, and the day begins with a criticality-ranked review of every inferred decision, each with a reason and a reversal
- [ ] **Phase 4: One pack for the daily session** - The session runs off one generated pack — the demonstration, the proposal, and a UAT handover — and its agreement becomes the next night's specifications
- [ ] **Phase 5: Generated, not hand-assembled** - The scope tracker and the weekly status report both come out of the planning tool's own data
- [ ] **Phase 6: The handover site says what each area is for** - Every content area carries an explicit organisation and marking, and progressive reveal ships
- [ ] **Phase 7: Close the two open return paths** - Transcription feeds the planning tool during a session, and post-signature review feedback re-enters the requirements record
- [ ] **Phase 8: Hardening — the signature apparatus leaves the kit** - No round writes or gates on a sheet signature; git's history is the record

## Phase Details

### Phase 1: Open the sixth stage and dispatch the night
**Goal:** The pipeline declares a sixth stage that continues past the published handover site into the delivery build, and a day's agreed work is dispatched into it at the end of the working day to run with nobody present.
**Mode:** mvp
**Requirements:** PLAN100-10, NIGHT100-10

**Success Criteria** (what must be TRUE):
1. The pipeline and the repository's front door both describe six stages, and the sixth names the delivery build that follows the handover site — neither still declares five.
2. A reader can follow the signed requirements package from the planning tool into the delivery stage with no hand step in between.
3. The practitioner runs one dispatch round at the end of a working day and leaves; the work continues without anyone pressing buttons or keeping a machine awake.
4. The delivery stage's own handoff states what the stage is handed and what it declares as output.

**Assumptions this phase rests on:**
- **The sixth stage is one prompt kit, not two.** The alternative the planning session weighed was
  a separate execution kit and delivery kit. One kit was adopted so the stage has one handoff and
  one declared-outputs list. If that is wrong, the four rounds Phase 2 to Phase 5 create split
  across two directories and each needs its own handoff — the phases do not change, but the file
  layout does.

**Decides:**
- **Decision 2 — what is the sixth-stage directory actually called? Decide during this phase.**
  The working name is `prompts/delivery/`, adopted by the planning session so the sixth stage is
  one kit and not two, after two prior analyses named it differently (`prompts/execution/` was the
  other). **It is a working name and not the practitioner's decision.** It is decided here because
  this phase is what creates the directory, and every later phase writes into it. Two consequences
  of the working name are already baked in and are his to accept or change: the round files run
  `D04` to `D06` rather than sorting into the order the day runs them, because `D01` to `D03` were
  minted first and renumbering them would churn four other rows for nothing; and `D06`, a
  reporting-and-handover round, sits inside the delivery kit because the register proposes no
  reporting kit. The blast radius is in the appendix, with the measured count of places the name
  is spelled.

**Notes for planning:**
- **Depends on:** Nothing (first phase)
- **Plans:** 2 plans
  - [ ] 01-01-PLAN.md — Sixth-stage delivery kit: `prompts/delivery/` directory,
    `HANDOFF.md`/`D01-dispatch.md` wired end-to-end, R-080 tracking note, reusable six-stage
    check script (immediately executable, no external file dependency)
  - [ ] 01-02-PLAN.md — Six-stage declaration in `PIPELINE.md`, `README.md`, and
    `prompts/documentation/HANDOFF.md` (precondition-gated on the user supplying these three
    currently-absent files)
- **This phase is the root of the delivery half.** The sixth-stage directory it creates is where
  NIGHT100-20 to NIGHT100-50, MORNING100-10 to MORNING100-60, DEMO100-10 to DEMO100-40 and
  REPORT100-10 all write. Nothing in Phases 2, 3, 4 or 5 can land before it.
- **What the new stage falsifies is already located, so the phase does not have to rediscover
  it:** the five-stage claim at `PIPELINE.md:3` and at `README.md` lines 6, 16, 27 and 54, and at
  `prompts/documentation/HANDOFF.md:192`. Those are this phase's work.

---

### Phase 2: A night that bounds itself
**Goal:** An unattended run is entered on purpose rather than by default, checks its own work and reassigns what fails, stops when it breaks a gate, and states in one place which acts belong to the automation and which stay with a human.
**Mode:** mvp
**Requirements:** NIGHT100-20, NIGHT100-30, NIGHT100-40, NIGHT100-50

**Success Criteria** (what must be TRUE):
1. The practitioner enters overnight mode through a round of its own that asks what the night's run takes, and the round then dispatches that selection.
2. A night's run finds its own failures through a second checking agent, reassigns them, and exits either when everything passes or when only documentation and low-level issues remain — bounded, and never open-ended.
3. A run that breaks a gate stops and waits, so the morning starts with a named failure instead of a silent workaround to discover.
4. Any reader of the dispatch round can say which acts the automation performs — moving and transforming data, writing and changing code, running tests, preparing and proposing work — and which are reserved to a human: approving, deciding, releasing.

**Assumptions this phase rests on:**
- **Five attempts, or a remainder of documentation and low-level issues only, is a sufficient bound
  on an unattended verification loop.** Both are stated values and **no measurement supports
  either** (RAID `A-020`). If the five is too low the loop ends with real work unfinished and the
  morning inherits it; if too high, a loop that can make no progress burns a night. Build the bound
  as a value that can be changed, and record what the first runs actually needed.

**Decides:**
- **Decision 1 — what are the severity levels, and is it one vocabulary or two? Decide during this
  phase.** Success criterion 2's second exit bound — "only documentation and low-level issues
  remain" — **is not checkable without a severity classification the harness does not have.** The
  same vocabulary is what Phase 3's criticality ranking needs. Whether one vocabulary serves both,
  and what its levels are, is undecided and is RAID issue `I-030`. **Deciding it here and reusing
  it in Phase 3 is the cheapest order**, because this phase is the first consumer. The blast radius
  is in the appendix.

**Notes for planning:**
- **Depends on:** Phase 1
- **Plans:** TBD
- Two open items bite here, and they are one decision rather than two: the five-attempt bound and
  the "documentation and low-level issues only" bound are both stated values with no measurement
  behind either, and the second is not checkable at all without the severity classification
  Decision 1 settles.

---

### Phase 3: The morning opens on ranked decisions
**Goal:** The night is closed by a round of its own, and the working day opens on a criticality-ranked review of every decision the run inferred, each carrying the reason it chose as it did and how to reverse it — with the day's lessons and problems recorded as they arise rather than recalled later.
**Mode:** mvp
**Requirements:** MORNING100-10, MORNING100-20, MORNING100-30, MORNING100-40, MORNING100-50, MORNING100-60

**Success Criteria** (what must be TRUE):
1. The practitioner closes the run and enters morning mode through a round of its own, in which he selects what the morning takes from the night.
2. Every decision the run inferred, or would have asked about, appears in a log with its reason and its reversal — a reviewer can act on any entry without reconstructing it.
3. The morning review presents those entries highest-criticality first, so the reviewer reads what matters without reading everything.
4. The review ends with a lessons step whose agreed output is written into the repository, and a lesson can be promoted from this engagement to the harness itself.
5. A problem hit during the day is logged when it happens and is still there at the retrospective — nobody relies on memory for it.

**Assumptions this phase rests on:**
- **A decision log written by an unattended run can carry a usable reversal for every entry.** The
  practitioner's own loop did this, which is the evidence, but it ran on his work rather than on a
  client delivery. If an inferred decision turns out to have no clean reversal, criterion 2 has to
  admit an entry that states so rather than silently omitting it — otherwise the log quietly becomes
  a list of the reversible half.

**Decides:**
- **Decision 1 returns here — the ranking half.** Success criterion 3 cannot be built without the
  severity vocabulary Phase 2 settles (`I-030`). **If Phase 2 decided two vocabularies rather than
  one, this phase inherits a second one to define and criterion 3's ordering has to be written
  against it.** The decision is the same item; this is its second consumer, and that is why it is
  cheapest to close it in Phase 2.

**Notes for planning:**
- **Depends on:** Phase 2
- **Plans:** TBD
- **The review is the answer to a named risk.** Risk `R-010` is that the more work is pushed to
  the model, the more the single human reviewer becomes the bottleneck; the ranking in criterion 3
  is what keeps that survivable, so it is load-bearing and not cosmetic. The decision log in
  criterion 2 is written by the dispatch round of Phase 1 and read by the review round of this
  phase, so it spans both.

---

### Phase 4: One pack for the daily session
**Goal:** The daily session runs off one generated pack — what the night built, what is proposed next, and something a business tester can act on — and the agreement reached in the session is written as the specification the next night's dispatch consumes, closing the delivery loop.
**Mode:** mvp
**Requirements:** DEMO100-10, DEMO100-20, DEMO100-30, DEMO100-40

**Success Criteria** (what must be TRUE):
1. One interactive round builds the whole pack from the planning data, asking the practitioner what the pack contains; nobody writes the session's materials by hand.
2. The pack shows what the overnight run built, with the features worth demonstrating chosen in the round — because the planning data records what was built and not what is worth showing.
3. The pack states what is proposed next, and the session's agreement becomes the specification handoff the dispatch round reads, so the next night's input is the last day's decision.
4. The pack carries a UAT handover short enough for a business tester who holds a day job to act on in the time they have.

**Preconditions:**
- **The client's testers must give time alongside their day jobs, for every delivered feature, at
  the pace this harness sets** (RAID `D-010`). **This is outside the repository's gift.** This phase
  can produce the handover; it cannot produce the tester. If the time is not given, criterion 4
  still passes — the document exists and is short — and the capability still fails in use. Record
  that distinction in the plan rather than letting a green criterion imply a working loop.

**Assumptions this phase rests on:**
- **One pack serves all three parts and one round builds it.** The alternative is three artifacts
  with three rounds. One was chosen because the three parts share a subject — the night just
  finished — and a single round asks its questions once. If the UAT handover turns out to need a
  different audience, a different cadence or a different distribution, it separates, and criterion 4
  moves with it.

**Notes for planning:**
- **Depends on:** Phase 1
- **Plans:** TBD
- **Sequenced after Phase 3, dependent on Phase 1.** The pack's subject is the run Phase 1
  dispatches, and the specification handoff in criterion 3 is written for that same dispatch
  round. It is placed after the morning review because a session reports a night the practitioner
  has already closed and read.

---

### Phase 5: Generated, not hand-assembled
**Goal:** The two artifacts the pod currently types — the scope tracker and the weekly status report — are produced from the planning tool's own phases, plans and roadmap instead.
**Mode:** mvp
**Requirements:** SITE100-10, REPORT100-10

**Success Criteria** (what must be TRUE):
1. The scope tracker on the handover site is produced from the planning tool's phases and plans, and a reader can trace any tracker row back to the plan it came from.
2. A refresh reproduces the tracker rather than a person rewriting it; no round writes tracker content directly any more.
3. A weekly status report is produced against a fixed template by a round in which the practitioner selects its contents — weekly, and plainly separate from the daily session pack.

**Assumptions this phase rests on:**
- **The planning tool's phases and plans carry everything a tracker row needs.** Criterion 1 assumes
  the mapping is total. If a tracker column has no source in the planning data — a MoSCoW rating is
  the obvious candidate, since the session's own sequence is *generate, then MoSCoW* — that column
  is either derived at generation time or stays a human act, and criterion 2's "no round writes
  tracker content directly" needs the exception named rather than discovered.

**Decides:**
- **Decision 3 — is the tracker round interactive, or is the tracker a whole carry? Decide during
  this phase.** Round 10 read SITE100-10 against the practitioner's interactive-generation rule and
  **left it silent, calling it the closest call on the sheet and flagging it for him.** The tracker
  IS generated, and it is NOT among the four artifacts he named. It was left silent because its
  contents are the planning tool's own phases and plans carried whole, and **a selection over the
  tracker would break the traceability the tracker exists for** — criterion 1 says a reader can
  trace any tracker row back to the plan it came from, and a curated tracker cannot promise that.
  The round's own words: *"If he wants the rule to reach it, that is his call and it is one cell."*

**Notes for planning:**
- **Depends on:** Phase 1
- **Plans:** TBD
- The weekly report's round lives in the sixth stage, which is why this phase depends on Phase 1;
  **the tracker half depends on nothing** and can be planned and built independently of the
  delivery work.

---

### Phase 6: The handover site says what each area is for
**Goal:** Every content area of the handover site carries an explicit organisation and an explicit marking, and progressive reveal ships on the areas marked for it — so a human reader sees a deliberately organised page, and the additional context given to the model sits beneath it rather than nowhere.
**Mode:** mvp
**Requirements:** SITE100-20, SITE100-40, SITE100-30

**Success Criteria** (what must be TRUE):
1. A reader opens each content page and finds it deliberately organised, page by page, rather than a dump of what happened to be generated.
2. Each content area carries a recorded marking — progressive-reveal or human-facing — held beside the area itself, so the marking cannot drift from the thing it marks.
3. On an area marked for reveal, a reader can open the additional context made available to the model beneath what the page shows a human, and close it again.

**Assumptions this phase rests on:**
- **Every content area falls cleanly into one of two markings.** The rule admits
  progressive-reveal or human-facing and nothing else. If an area needs both — a human-facing
  summary with model context beneath it on the same area — then the marking is not a binary and
  criterion 2's "a recorded marking" becomes a recorded pair. Settle that during SITE100-20, because
  SITE100-40's configuration field takes its shape from the answer.

**Decides:**
- **Nothing open is deferred to this phase, but criterion 2's content is decided INSIDE it.** Which
  areas take progressive reveal and which are human-facing is RAID issue `I-010`, and it is **not a
  question to answer before planning** — it is the OUTPUT of the clean-up pass. That distinction is
  the phase's hard constraint and is stated under Notes below.

**Notes for planning:**
- **Depends on:** Nothing (board-side; sequenced here because the delivery half has the dependency
  root and this half does not)
- **UI hint:** yes
- **Plans:** TBD
- **A hard chain runs inside this phase, in this order.** The per-area organisation decision is
  the OUTPUT of the content clean-up pass and not an input to it (`I-010`); the marking records
  that decision; and progressive reveal has no input at all without the marking. So SITE100-20
  runs first, SITE100-40 records what it decided, SITE100-30 builds on the record. The three
  cannot be reordered or run in parallel.

---

### Phase 7: Close the two open return paths
**Goal:** The two places where a live human event should reach the requirements record, and today does not, are designed and closed: a session's transcription feeds the planning tool while the session is still running, and feedback from a review meeting held after the workbook was signed re-enters the documentation stage as a source in its own right.
**Mode:** mvp
**Requirements:** CAPTURE100-10, KIT100-10

**Success Criteria** (what must be TRUE):
1. Planning and research begin while a workshop session is still running, fed by that session's own transcription rather than by a pass after it ends.
2. The feasibility of that live feed is settled and recorded either way — the harness does it in the time available, or the record says why it cannot and what stands instead.
3. Findings from a post-signature review meeting enter the documentation stage as their own source, and the registers and the tracker are corrected against them without a single identifier being renumbered.

**Preconditions:**
- **The feasibility of a live transcription feed has to be established, and it is not this
  phase's to grant.** It depends on what a transcription service can deliver into the planning tool
  inside a running meeting. Criterion 2 is written so that the phase closes either way.

**Assumptions this phase rests on:**
- **Transcription can feed the planning tool during a session in the time available** (RAID
  `A-010`). **The speaker states he does not know whether it can be done by then.** If it cannot,
  criterion 1 does not ship and criterion 2 carries the phase — the record says why, and what stands
  instead. Plan for that outcome explicitly rather than treating it as a failure state.
- **A return path that exists will be walked.** Risk `R-020` says otherwise: the change register was
  assessed as useful at the first client review and under-used afterwards, and the RAID register was
  not chased to the end. **A return path nobody walks is the failure mode to design against**, which
  makes criterion 3's "without a single identifier being renumbered" a usability requirement as much
  as a correctness one — an identifier that moves is a reason not to come back.

**Notes for planning:**
- **Depends on:** Nothing (both paths are independent of the delivery half)
- **Plans:** TBD
- **This is design work before it is implementation.** CAPTURE100-10's feasibility is
  unestablished and is carried as assumption `A-010`. KIT100-10's return path exists in no form —
  the apply-changes round accepts only findings the kit's own validation rounds raised and signed,
  and the round KIT100-10 needs is undesigned. Risk `R-020` bears on it: the registers were
  assessed as useful at the first review and under-used afterwards, so a return path nobody walks
  is the failure mode to design against.
- `R-020`'s source is `S-01 01:15:08`, where the practitioner sets the registers against the
  tracker: "the change register is helpful to set context and sign off from the client that we
  captured their intent properly. The RAID just to make sure things don't fall between the lines.
  But our main sort of leverage we're going to get out of this is the scope tracker and the
  testing."

---

### Phase 8: Hardening — the signature apparatus leaves the kit
**Goal:** No round writes a digest-and-token row for a sheet and no round gates on one; the repository's own history is what a later reader consults for what a sheet said and when, and the practitioner's acceptance is recorded by the round that asked for it.
**Mode:** mvp
**Requirements:** KIT100-20

**Success Criteria** (what must be TRUE):
1. No round in the documentation kit or the planning kit writes a sheet signature, and no round gates on one; nothing in the pipeline or the contracts still declares a signature record.
2. The handover boundary still holds: a sheet the practitioner has accepted is no longer a draft, and a later change to it goes through the apply-changes round — carried by the `Accepted:` line in the round's provenance note and by the commit that recorded the act.
3. The per-finding `Signed` column still gates the apply-changes round — it is a different mechanism, it is out of this phase's scope, and it did not leave with the rest.
4. The board's own tests agree with the change rather than asserting the old apparatus.

**Preconditions:**
- **The removal is scheduled for the hardening stage on the practitioner's own instruction**, and
  that instruction is the reason this phase is last rather than any dependency. If the receiving
  team wants it earlier, that is his call to change and not a sequencing error to correct.

**Assumptions this phase rests on:**
- **The `Accepted:` line and the commit are sufficient to carry the handover boundary.** The
  argument for it is stated and is sound: it is the same shape as a line the audit rounds already
  write. **It has not been exercised.** If a later reader cannot tell from the provenance notes and
  the commit history which sheets were accepted and when, the boundary has been weakened rather than
  moved, and criterion 2 has passed on the mechanism rather than on the outcome. **Test criterion 2
  by asking the question of a real repository, not by checking the line exists.**

**Decides:**
- **Decision 4 — what happens to the per-finding `Signed` column? Decide during this phase, and
  decide it BEFORE the removal sweep runs.** Criterion 3 says the column stays. **What it does not
  say is whether the column should exist at all**, which is a separate question the practitioner
  carried away as a backlog item. The two questions have to stay apart: this phase's job is that the
  column **survives** the sweep. **Its pointer has no target inside the package** — see the appendix.
  If the answer is that the column also goes, that is new scope with its own row, not an extension
  of KIT100-20.

**Notes for planning:**
- **Depends on:** Nothing (no phase produces an input to it; it is sequenced last by the
  practitioner's instruction that the removal belongs to the hardening stage)
- **Plans:** TBD
- **Last by the practitioner's explicit instruction.** This row is scheduled for the hardening
  stage and belongs in the final phase. It touches twelve or more files across both prompt kits,
  the contracts, the pipeline and three board test files, so it is a wide, shallow change and the
  risk in it is criterion 3: the `Signed` column reads like part of the same apparatus and is not.

---

## Appendix

### Open decisions

The questions still to be answered, collected from the **Decides** blocks of the phase entries —
not every phase has one. Each names the phase it must be decided by, and states its blast radius as
consequences rather than as a warning.

| Decision | Decide by | What hangs on it |
|---|---|---|
| **Decision 1** — what are the severity levels, and is it one vocabulary or two? | **Phase 2**, reused in **Phase 3** | RAID `I-030`. Two success criteria are unbuildable without it: Phase 2's criterion 2, whose second exit bound — *only documentation and low-level issues remain* — is not checkable without a classification the run can apply to its own findings; and Phase 3's criterion 3, whose ranking has nothing to rank by. **One vocabulary serving both is the cheap answer and is what the RAID row proposes**; two vocabularies double the definition work and create a translation between the run's own severity and the reviewer's criticality. Deciding it in Phase 2 costs one decision; deferring it to Phase 3 means Phase 2 ships an exit bound that cannot be evaluated, which is the same as shipping only the five-attempt bound. **Reversal:** the levels live in the dispatch round's clauses and the review round's ordering — changing them is an edit to two files, cheap while no run history depends on them and progressively less so afterwards. |
| **Decision 2** — what is the sixth-stage directory actually called? | **Phase 1** | `prompts/delivery/` is a **working name adopted by the planning session, not the practitioner's decision.** It was chosen over `prompts/execution/` so the sixth stage is one kit and not two. **Two consequences ride on it** and are his to accept or change: the round files run `D04` to `D06` rather than in the order the day runs them, because `D01` to `D03` were minted first; and `D06`, a reporting-and-handover round, sits inside the delivery kit because the register proposes no reporting kit. **The measured blast radius, stated rather than estimated:** inside this package the string is spelled **twenty times across sixteen lines of `REQUIREMENTS.md`**, twice in `PROJECT.md` and once in `STATE.md`, and **not at all in this roadmap**, which says *the sixth-stage directory* throughout. **So the claim that it is "recorded in one place so it can be changed in one place" is not true of this package**, and this appendix row is the correction: **this row is the single decision record; the twenty-three spellings are consumers of it.** **Reversal:** a rename across those twenty-three occurrences, plus the directory itself, before Phase 2 writes into it. After Phase 2 the cost rises with every round file added. |
| **Decision 3** — is the tracker round interactive, or is the tracker a whole carry of the planning tool's phases and plans? | **Phase 5** | SITE100-10 was **deliberately left silent** on the practitioner's interactive-generation rule and **flagged to him as the closest call on the register.** The tracker IS generated and it is NOT among the four artifacts he named. **If it stays a whole carry**, Phase 5's criterion 1 holds as written — a reader can trace any tracker row back to the plan it came from. **If a selection is introduced**, that traceability is broken by construction: a curated tracker cannot promise that every row has a plan behind it, and criterion 1 has to be rewritten. The round that flagged it recorded the size of the change: *"If he wants the rule to reach it, that is his call and it is one cell."* **Reversal:** one cell on the register and one clause in the generator, but criterion 1 moves with it — so decide before Phase 5 is planned, not during it. |
| **Decision 4** — what happens to the per-finding `Signed` column? | **Phase 8** | **Not the same question as KIT100-20**, and the phase depends on the two staying apart. Phase 8's criterion 3 asserts the column **survives** the removal sweep, because it gates the apply-changes round and reads like part of the apparatus being removed. Whether the column should exist at all is a separate question the practitioner carried away as a backlog item. **That pointer has no target inside this package** — see below. **If the answer is that the column also goes**, it is new scope with a row of its own, and the apply-changes gate needs a replacement named before it is removed. **Reversal:** while the two questions stay separate, trivially — criterion 3 is a check that a thing still exists. Once a sweep has taken the column by association, restoring the gate means restoring a mechanism nothing else records. |
| **Decision 5** — is the harness being used to change itself, and is that a risk this engagement should carry on its sheet? | **Before Phase 1 is planned** | **This decision appears in none of the four planning files, and this row is the first place it is written down.** The practitioner raised it while this engagement was being set up: **every requirement in the transcript changes the harness that is shown to clients, and the harness is being used to change itself.** The RAID round judged it a real risk that belongs on the sheet and **deliberately did not mint it**, for a stated reason: it is in neither source — it was said to an agent in conversation and no line of the practitioner's notes carries it — and **writing it would have put an uncited row on a sheet whose value is that every row can be checked against something.** The trigger has fired **five times** (rounds 6, 8, 9, 10 and 11) and each round re-measured the condition with a control term in the same run and found it still unmet. **The trigger is a condition, not a schedule: the row is minted as `R-080` at the first round after the concern appears in a source.** **What hangs on it:** the concern is live whether or not it is minted, and it bears on every one of the eight phases — the engagement's subject is this repository, and a harness change reaching the template's default branch reaches every other engagement's live site too. The practitioner has already taken that deliberately — *"I want it to flow out to every client. Nothing needs to freeze."* **Reversal:** the brake exists and is not being used. A `.handover-freeze` file at the root of an engagement branch holds that one branch; a `.handover-freeze-all` file on the default branch holds them all. Either can be added later, in a commit, without undoing anything. **To close this decision:** the practitioner confirms the wording, it is appended to his notes under a new dated heading — which that file is explicitly designed to take — and `R-080` is minted. |

### Decisions taken during planning, and where each one lives

Closed decisions, recorded here so none of them is lost between the planning session and the team
that builds from this package. A closed decision that surfaces nowhere is re-opened by the next
round that meets its subject.

| Decision | Taken | Where it lives, and what it governs |
|---|---|---|
| **Scope is the register's 24 rows**, not the 24 `In` rows of the scope-decision record | 2026-09-20 | The practitioner ran an explicit scope test — *does this cause a file in this repository to change, be deleted or be created?* — and it cut 78 rows to 24. The struck items are ways of working, not build work. **They are listed under Out of Scope in `PROJECT.md` and `REQUIREMENTS.md`.** **One limit is recorded with it and does not transfer:** that test needs the codebase in hand, so it was available only because this engagement's subject was its own repository. A normal engagement uses the change register's own purpose test instead — does this row describe a change to how the business works, awaiting the business's approval — which needs no code at all |
| **Phases are ordered by dependency**, each delivering a visible outcome | 2026-09-20 | The practitioner's call. The sixth-stage directory must exist before five rules can write clauses into files inside it; the board-side work depends on nothing and follows. **It governs [How this roadmap is ordered](#how-this-roadmap-is-ordered) and every `Depends on` line.** Re-deriving the phase order is out of scope for any later round |
| **Two identifier namespaces, with a mapping between them** | 2026-09-20 | The change register owns `CR-010` to `CR-240`, the business's namespace, and it does not move. The roadmap and the requirement cards own family identifiers, the delivery namespace the site renders and groups by. **This corrects an earlier decision that the two were one namespace carried verbatim.** That reading could not survive contact: the site's identifier grammar is family code, group number, hyphen, item number, and a flat `CR-010` satisfies none of the five rules that enforce it — measured against the parser, with a conforming control in the same run. Renumbering the register was refused, because the register is the business's approval view and traceability depends on its string. **The mapping is therefore written in both directions in one pass** — the register's `Delivery ID` column and `REQUIREMENTS.md`'s change-record column — so neither can drift from the other. Both namespaces stay mint-once. It governs [Coverage](#coverage) and `REQUIREMENTS.md`'s traceability table |
| **The evidence travels with the requirement, on its card, not with the phase** | 2026-09-20 | Decided in three steps in one sitting. The roadmap was first written in the standard shape with the evidence held for a later stage; the practitioner then asked for the evidence to travel with the roadmap; and he then measured the roadmap against what a reader needs and reversed that: *"I think we have good content at the phase level ... the gap is only at the requirement card level."* **So the phase level keeps the vanilla bands — goal, success criteria, decisions, preconditions, assumptions, notes — and the per-requirement evidence lives on the requirement card.** **It governs the 24 cards under `analysis/requirement-detail/` and the phase bodies in this file.** One condition rides with it and is the important half: **evidence always, because the sources are always present; file mapping only where the code is available.** Where a codebase is not yet in hand there is no file column at all, and the mapping becomes planning-stage work done when access lands |
| **The handover carries its own evidence, and the site and the zip must agree** | 2026-09-20 | The published package carries the evidence behind its requirements, including the raw sources, so a citation can be followed rather than believed. It resolves a straight inconsistency: the handover site renders the raw workshop documents under a section named "The sources", and the downloadable package did not include them. **It governs [Where the evidence lives](#where-the-evidence-lives).** **One half of it was narrowed on the same day and the narrowing is the part that stands:** the raw sources travel, and the register sheets do not. They are intermediate working files on the way to a Google Sheet that becomes the source of truth for the values people edit, so the evidence a requirement rests on travels on that requirement's card and no planning file names a sheet as a path. **Blast radius, taken deliberately:** a raw working-session transcript is the most sensitive artifact an engagement holds. Here it is the pod's own recording. On a client engagement it is a room full of that client's staff, so whether it travels is a per-engagement decision rather than a default — the mechanism ships it, the practitioner rules each time |
| **KIT100-20 is scheduled last** | 2026-09-19 | The practitioner's own instruction, given inside the quotation the row cites. **It governs Phase 8's position**, which rests on no dependency. A later round that re-sequences by dependency alone will move it and will be wrong |
| **No general "all generation is interactive" rule; each generating row states its own mechanism** | 2026-09-20 | The practitioner struck the general rule mid-round: *"if it's a universal thing, then there'd be confusion at which one it applies to."* **His reason is the operative part:** a row that reads *generated from the planning data*, sitting beside a separate rule that reads *and all generation is interactive*, is read correctly only by a reader who joins the two; a row that reads *an interactive round produces it* cannot be misread. **The cost is recorded rather than discovered:** the sentence repeats on four rows, and a fifth generating row added later can be written without it and nothing will catch the omission |
| **The handover instruction: place the planning directory and run plan-phase for Phase 1** | 2026-09-20 | **Measured, not argued.** The new-milestone command — the natural guess, and the one the practitioner made himself — does not consume an existing roadmap; its own description says it creates or updates the requirements and roadmap files, so running it on this package regenerates both and **discards everything this engagement produced.** That command's own text names plan-phase as its successor. **It lives in `STATE.md`'s handover note and in `PROJECT.md`'s constraints**, and it belongs in the package README |

### External preconditions

Outside work the build waits on, collected from the **Preconditions** blocks — not every phase has
one. None is a requirement; each is a permission, a grant or a check.

| Precondition | Gates | Why it matters |
|---|---|---|
| **The client's testers give time alongside their day jobs** (RAID `D-010`) | **Phase 4** | For every delivered feature, at the pace this harness sets. **Outside this repository's gift.** Phase 4 can produce the UAT handover; it cannot produce the tester. Criterion 4 can pass — the document exists and is short — while the capability fails in use, so the plan must keep the two apart |
| **The feasibility of a live transcription feed into the planning tool** (RAID `A-010`) | **Phase 7** | The speaker states plainly that he does not know whether it can be done in the time available. Criterion 2 is written so the phase closes either way: the harness does it, or the record says why it cannot and what stands instead |
| **The practitioner confirms the self-modification concern in a source** | **Decision 5**, project-wide | `R-080` is minted at the first round after the concern appears in a source, and the condition has been re-measured and found unmet five times. It needs one appended dated heading in the practitioner's notes. Until then the risk is live and uncited |
| **The practitioner assigns owners to the RAID rows** | All phases that carry a RAID row | `Owner` is empty on every one of the seven rows **by decision** — an owner is assigned at the review meeting he holds after reading the sheet. A phase planner should not invent one |

### Assumptions

The load-bearing guesses, collected from the **Assumptions** blocks — not every phase has one —
plus the two that belong to no single phase. An item lands here only when it is neither an open
decision nor an external precondition: if it needs an answer it is the first, if it is outside work
it is the second.

**Ten rows: two are RAID rows, two are measured or sourced, and six are this enrichment's own
inferences. The difference is marked in the table.** `A-010` and `A-020` are RAID rows with a
source and a locus — the practitioner or the session said them. The last two rows carry their own
measurement. **The six rows marked *inferred* were surfaced by reading each phase against its
requirements, and no source states any of them.** They are load-bearing all the
same: a design decision rests on each, and none has been tested. **A planner may overturn an
inferred assumption on evidence without going back to the practitioner; overturning `A-010` or
`A-020` changes what a source says the requirement is, and does not.**

| Assumption | Bites at | If it is wrong |
|---|---|---|
| Five attempts, or a remainder of documentation and low-level issues only, is a sufficient bound on an unattended run (RAID `A-020`) | Phase 2 | Both are stated values and no measurement supports either. Too low and the loop ends with real work unfinished; too high and a loop that cannot progress burns a night. Build the bound as a changeable value and record what the first runs needed |
| Transcription can feed the planning tool during a session in the time available (RAID `A-010`) | Phase 7 | Criterion 1 does not ship and criterion 2 carries the phase |
| *(inferred)* The sixth stage is one prompt kit, not two | Phase 1, and the file layout of Phases 2–5 | The four rounds split across two directories, each needing its own handoff. The phases do not change; the layout does |
| *(inferred)* A decision log written by an unattended run can carry a usable reversal for every entry | Phase 3 | The log quietly becomes a list of the reversible half. Criterion 2 must admit an entry that states it has no clean reversal |
| *(inferred)* One pack serves all three parts of the daily session, built by one round | Phase 4 | The UAT handover separates into its own artifact, cadence and distribution, and criterion 4 moves with it |
| *(inferred)* The planning tool's phases and plans carry everything a tracker row needs | Phase 5 | A column with no source in the planning data — a MoSCoW rating is the candidate, since the session's own sequence is *generate, then MoSCoW* — is either derived at generation or stays a human act, and criterion 2's "no round writes tracker content directly" needs the exception named |
| *(inferred)* Every content area falls cleanly into one of two markings | Phase 6 | The marking is a pair rather than a binary, and SITE100-40's configuration field takes a different shape. Settle it during SITE100-20 |
| *(inferred)* The `Accepted:` line and the commit are sufficient to carry the handover boundary | Phase 8 | The boundary is weakened rather than moved, and criterion 2 has passed on the mechanism rather than on the outcome. Test it by asking a real repository which sheets were accepted and when |
| Both sources are Authoritative, and neither contradicts the other | Every phase | **Measured, not assumed:** the normalisation round found no conflict — the two sources address different subject matter and nowhere contradict one another, so no register row records two positions. S-02 is practitioner-authored with **no recording behind it**, tiered Authoritative by his own decision at capture, and that is recorded rather than left to be inferred |
| The reading rule holds: the boundary at `S-01 01:26:28` marks emphasis, not a cut | Phase 7 most sharply, and the scope boundary generally | Two harness proposals sit after that boundary, and CAPTURE100-10 is one of them. A round that read the boundary as a cut would drop both — and one row of the scope-decision record exists only because the boundary is soft, and says so |

### Glossary terms in play

The canonical terms this roadmap's language depends on. The full sheet — 28 terms, 26 resolved and
2 unresolved gaps, each with the variants seen and the source it was resolved against — is a working
register in the engagement's own lane and does not travel with this package. The terms in play for
one requirement are named on that requirement's card.

| Term | In play at | The sense the session used |
|---|---|---|
| **Harness** | All phases | The pod's own tooling and process for running AI-delivery engagements — prompt kits, the planning tool, the handover site, the autonomous run loop and the review rituals. **The project under specification is the harness itself** |
| **GSD** | 1, 2, 5, 7 | The planning tool that produces phases, milestones, roadmaps and plans |
| **Overnight mode** | 2, 3 | One of four named modes of the practitioner's run loop. In overnight mode the orchestrator logs every decision it inferred or would have asked about; in morning mode it walks him through them one at a time with the reason and the reversal |
| **Morning report** | 3 | A first-thing-in-the-morning account of what ran overnight. Two proposals attach to it in the session: classify entries by criticality so the highest-value ones are reviewed first, and a lessons-learned step whose agreed output is saved into the repository and can be promoted to the harness |
| **Cognitive load** | 2, 3 | The reviewer's burden when reading what the agents produced. **Treated as the binding constraint on delivery speed** — "the bigger and bigger things you push to the AI, the bottleneck becomes human" |
| **Daily sprint** | 1, 4 | A one-day cycle: demo at noon, feedback turned into issues and specs, work dispatched at about four, agents run overnight, review in the morning. The client-facing part is framed as a 90-minute session combining demo, planning and a walkthrough of how the work is done today |
| **Vertical slice** | 4 | One thin path through every layer that delivers usable value, as against a horizontal slice that completes one layer across all features. The session's retrospective finding is that the prior engagement sliced horizontally by accident and met its hardest integration work last |
| **Scope tracker** | 5, 7 | The spreadsheet carrying the scope statements and their MoSCoW ratings, which the handover site reads. **Named by both parties as the artifact with the most leverage of the four** |
| **MoSCoW** | 5 | Must, Should, Could, Won't. The transcript renders it "Moscow" throughout — a speech-to-text mis-capture of the acronym, canonicalised so every downstream row is consistent |
| **Change register** | 7, 8 | The log of changes and rules agreed with the client. **Its purpose, in the practitioner's own words, is the test of whether any row belongs in it:** it records the move from the existing way of working to the intended one, for the business to approve — a restatement of the same scope the tracker carries from a different angle, which is why traceability runs between the two |
| **RAID** | 7 | Risks, assumptions, issues and dependencies |
| **Progressive reveal** | 6 | A presentation device on the handover site that exposes the additional context made available to the AI beneath what a human reader consumes. Requested for the client view as the first step toward role-based views |
| **Role-based view** | 6 | A view of the handover site selected by the reader's role — named at capture as developer, client, CPO and AI. **The near-term scope is a client view plus progressive reveal; the full set is the eventual goal** |
| **Pod program** | 1 | The programme under which the two partner firms deliver portfolio-company projects, working together as one pod. Named once in the transcript and defined nowhere in it; resolved by the practitioner on 2026-09-19 and appended to S-02 |

**Two terms are unresolved gaps and neither was guessed.** An open context-file standard named in
the session, whose promised article is in neither source — the claim that it exists is recorded, the
standard itself is unverified. And a prior engagement's domain vocabulary, kept in the glossary so a
reader can follow the session's worked examples and **never a harness requirement.**

### Pointers with no target inside the package

Stated here rather than left to be found by a reader who follows one.

| Pointer | Where it appears | Position |
|---|---|---|
| **The register sheets and their provenance notes** — the change register, the RAID sheet, the glossary, the scope-decision record, the decomposition, and the four provenance notes | Named in prose in `PROJECT.md`, in `REQUIREMENTS.md` and in this file — and as a path nowhere | **They do not travel with the package, and they will not.** They are intermediate working files in the engagement's own lane, on the way to a Google Sheet that becomes the source of truth for the values people edit; a copy of a working file inside a handover goes stale the day it ships. **What each of them holds about a requirement travels on that requirement's card instead** — the quotation, the reasoning, the judgment calls, the RAID links and the glossary terms. So the sheets are named in words and never as a path, and a reader who wants a row's evidence opens the card rather than looking for a file |
| **The backlog item carrying the `Signed`-column question** (Decision 4) | `REQUIREMENTS.md`, under KIT100-20 | **It has no target inside the package, and it will not get one.** The item lives in the engagement repository's own build-state directory, which the package's export rules exclude by design. **The question itself is therefore restated in full in [Open decisions](#open-decisions) as Decision 4**, so a reader of this package can act on it without the backlog. The citation is kept because it names where the practitioner's own copy lives; it is not a path this package resolves |
| **`R-080`** (Decision 5) | Nowhere, until now | **It is not minted and has no RAID row**, by a stated and re-measured decision — the concern is in neither source. Decision 5 is its only home in this package. **A reader looking for `R-080` on the RAID sheet will not find it, and that absence is correct** |
| **The declared hole in the RAID Issue numbering** | The seven-row RAID summary in `REQUIREMENTS.md` | The Issue block reads `I-010`, then `I-030`. **`I-020` is retired in place and its number is never reused.** The hole is declared in the RAID provenance note and is asserted by that round's own verifier, which treats an undeclared hole as a defect and a declared one as correct |

### Coverage

All 24 v1 requirements are mapped to exactly one phase each. Identifiers below are the delivery
namespace; each one's originating change record is in `REQUIREMENTS.md`'s traceability table and in
the register's own `Delivery ID` column.

| Phase | Requirements | Count |
|-------|--------------|-------|
| 1 | PLAN100-10, NIGHT100-10 | 2 |
| 2 | NIGHT100-20, NIGHT100-30, NIGHT100-40, NIGHT100-50 | 4 |
| 3 | MORNING100-10, MORNING100-20, MORNING100-30, MORNING100-40, MORNING100-50, MORNING100-60 | 6 |
| 4 | DEMO100-10, DEMO100-20, DEMO100-30, DEMO100-40 | 4 |
| 5 | SITE100-10, REPORT100-10 | 2 |
| 6 | SITE100-20, SITE100-40, SITE100-30 | 3 |
| 7 | CAPTURE100-10, KIT100-10 | 2 |
| 8 | KIT100-20 | 1 |

**Total: 24 of 24 mapped. No requirement is unmapped and none appears twice.**

**Every requirement carries its evidence on its own card**, one card per identifier under
`analysis/requirement-detail/`, and two cards carry a stated limit. NIGHT100-50 rests on a passage
that argues the automation boundary rather than stating it — the register's wording is a
restatement, and the card says so. SITE100-20, SITE100-30 and SITE100-40 all derive from one
capture passage, quoted in full on SITE100-20's card and cited from the other two, so the evidence
for the three is one quotation rather than three.

**Seven RAID rows stand, and all seven are attached to a phase.** `R-010` → Phase 3; `R-020` →
Phase 7; `A-010` → Phase 7; `A-020` → Phase 2; `I-010` → Phase 6; `I-030` → Phases 2 and 3;
`D-010` → Phase 4. **No RAID row sits unattached, and Phases 1, 5 and 8 carry none because no row
links their requirements.** Each row is named on the card of every requirement it attaches to.

## Progress

**Execution Order:**
Phases execute in numeric order: 1 → 2 → 3 → 4 → 5 → 6 → 7 → 8

| Phase | Plans Complete | Status | Completed |
|-------|----------------|--------|-----------|
| 1. Open the sixth stage and dispatch the night | 0/TBD | Not started | - |
| 2. A night that bounds itself | 0/TBD | Not started | - |
| 3. The morning opens on ranked decisions | 0/TBD | Not started | - |
| 4. One pack for the daily session | 0/TBD | Not started | - |
| 5. Generated, not hand-assembled | 0/TBD | Not started | - |
| 6. The handover site says what each area is for | 0/TBD | Not started | - |
| 7. Close the two open return paths | 0/TBD | Not started | - |
| 8. Hardening — the signature apparatus leaves the kit | 0/TBD | Not started | - |

---
*Roadmap created: 2026-09-20*
*`Decides` fields and the open-decisions appendix added: 2026-09-20*
*Per-requirement evidence moved onto the 24 requirement cards: 2026-09-20*
