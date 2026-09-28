---
id: CAPTURE100-10
tracker_id: CAPTURE100.10
title: "Feed the session live"
---

# CAPTURE100-10 — Feed the session live

> "Transcription feeds the planning tool during a session rather than after it, so planning and research begin while the session is still running."

MoSCoW and Status live in the shared Scope Tracker sheet, and the requirement's phase in `.planning/ROADMAP.md` — **look them up there; this card does not restate them.** The quotes below are the workshop-corpus record.

**Sources:** change record `CR-010` · locus `S-01 01:27:51`

## What this is for

Today a workshop ends and the analysis starts afterwards, so the room's own material sits idle for as long as the write-up takes. This requirement removes that wait: the planning work begins inside the session, and by the time the room breaks up there is something to look at rather than a queue. It changes the shape of a workshop day for the people running it, and it shortens the gap between what a client says and what they see back. It is the earliest point in the whole pipeline where time can be taken out.

## The evidence

**What the source says.**

> "I don't know if you guys have done this — I mean, almost like real time transcription feeding into an LLM... And so our conference [is] feeding GSD and it's going through the planning and the research, and instead of having to have that lag — I don't know if we can do that by that time — but maybe we could start thinking about how do we almost do real time interaction in a meeting to do this, as opposed to having to do it so serially."
> — the practitioner, `S-01 01:27:51`–`01:28:06`

**The speaker states his own uncertainty in the same sentence that states the requirement.** That is the single most important thing about this row, and it is why an honest negative is an acceptable outcome and a silent omission is not.

**The reasoning on the register.** The row was proposed in the session's second half and read in scope under the reading rule. **It carries one capability applied in several places, not several requirements:** an agent listens to a session while it runs and feeds what it hears into the work — in the documentation stage, in the planning stage and in the pod's own daily meeting. **An earlier reading placed this row under a workshop-preparation stage; that clause named a destination rather than the requirement, and it is gone with the stage.** The act this row describes happens during a live session, not before one.

**Judgment calls that bear on it.** The practitioner drew a boundary during the session between harness content and client preparation, and later ruled that the boundary **marks emphasis, not a cut** — the group went on producing harness ideas after the line was drawn. **This row is one of two proposals a round that stopped at the boundary would have dropped.** The rule was measured rather than asserted: harness vocabulary concentrates before the boundary but does not stop there.

**RAID rows linked to it.**

| ID | Type | What it says |
|---|---|---|
| `A-010` | Assumption | Half established, half not. Listening to a live session works today: the transcription service is connected as a tool and returns a point-in-time snapshot of a running meeting, so an agent can work on what has been said while the meeting continues. Talking back into the room does not: the agent has no voice and no seat, so a person relays until it has one |

The RAID sheet cites this row by its change record, `CR-010`, because that sheet has not moved.

**Glossary terms in play.** *GSD* — the planning tool that produces phases, milestones, roadmaps and plans. *Harness* — the pod's own tooling and process for running delivery engagements.

## Open items and watch-outs

- **Half the feasibility is established and half is not.** Listening works today and has been exercised: a transcription service connected as a tool returns a snapshot of a meeting while it is still running. What does not work is the return leg — the agent has no voice and no seat in the room — so a person relays its output until something gives it one. That half is outside this repository's gift.
- **Closing this requirement does not require it to work.** If the live feed cannot be done, the record has to say why and what stands instead. That outcome is planned for, not a failure state.
- A live feed puts a room's unedited words into a planning tool as they are spoken. Whether that is acceptable is a per-engagement decision about the room, not a technical one.

## Links

- The phase this sits in: `.planning/ROADMAP.md#phase-7-close-the-two-open-return-paths`
- Sibling cards: [KIT100-10](KIT100-10.md) is the other return path into the requirements record; [SITE100-10](SITE100-10.md) consumes the planning tool's output further down the same pipeline.
