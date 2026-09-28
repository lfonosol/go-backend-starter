---
id: REPORT100-10
tracker_id: REPORT100.10
title: "Generate the weekly status report"
---

# REPORT100-10 — Generate the weekly status report

> "Status reporting is generated weekly from the planning tool against a fixed template, by an interactive round in which the practitioner selects what the report contains, replacing hand-written updates."

MoSCoW and Status live in the shared Scope Tracker sheet, and the requirement's phase in `.planning/ROADMAP.md` — **look them up there; this card does not restate them.** The quotes below are the workshop-corpus record.

**Sources:** change record `CR-240` · locus `S-01 36:27` and `S-02 the mode transitions`

## What this is for

Stakeholders who are not in the daily session still need to know where things stand, and at this delivery speed writing that update by hand becomes its own bottleneck. The planning tool already holds the phases, the milestones and the roadmap the update needs, so this requirement builds the report from that data against a fixed template, with the practitioner choosing what goes in. The audience is the stakeholder outside the room; the cadence is weekly and deliberately so, because the daily meeting already covers the day. The same template every week also means a reader can compare one week with the next.

## The evidence

**What the source says.**

> "As the speed of development is huge, we also have to be very clear to the stakeholders that hey, yesterday this happened, today this happened, tomorrow it's this. And because we're all the time pushing new stuff — if we want to automate that, and of course we want to use GSD because it has the phases and milestones and roadmaps and so forth — the idea was that we would build an agent on top of GSD that would actually create these reports, and they would always be using the same template."
> — a delivery-team participant, `S-01 36:27`

> "Let us call it the weekly status report, because we have the daily meeting — the weekly status report."
> — the practitioner, `workshop-docs/practitioner-notes-2026-09-19.md` § *Capture — the mode transitions, and the weekly status report*

**The reasoning on the register.** **The stated cause is pace: with delivery this fast, hand-written reporting becomes the bottleneck.** **The cadence is weekly and the practitioner named it so in order to separate it from the daily meeting.** The session pack is the daily artifact and this is the weekly one; **they share neither rhythm nor mechanism.**

**Judgment calls that bear on it.** Both loci stand for a stated reason: the transcript is the origin of generated reporting, the notes are the cadence and the name. **Nothing on either sheet implied a daily status report, and that was measured rather than assumed** — the phrase occurs on one register row and on no RAID row. **One known discrepancy is recorded rather than left to be found:** the decomposition's reporting note still describes an agenda setter for the daily session, a half that was already superseded. That file was outside the round's write scope.

**RAID rows linked to it.** None. No row on the RAID sheet links this requirement.

**Glossary terms in play.** *GSD* — the planning tool holding the phases, milestones and roadmap. *Scope tracker* — the other generated artifact in the same phase. *Daily sprint* — the rhythm this report is deliberately not on.

## Open items and watch-outs

- **Its round lives in the sixth stage**, so this half of the phase waits on that stage existing. The tracker half does not.
- The round must propose a selection and let the practitioner change it. A round that reads the data and emits a report does not meet his stated test, however good the report.
- A fixed template is only useful if it survives contact with a week that does not fit it. Nothing here says what happens then.

## Links

- The phase this sits in: `.planning/ROADMAP.md#phase-5-generated-not-hand-assembled`
- Sibling cards: [SITE100-10](SITE100-10.md) is the other hand-assembled artifact becoming generated; [DEMO100-10](DEMO100-10.md) is the daily artifact this is deliberately separate from.
