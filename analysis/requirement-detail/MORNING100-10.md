---
id: MORNING100-10
tracker_id: MORNING100.10
title: "Open with the decisions"
---

# MORNING100-10 — Open with the decisions

> "The working day opens with a review of the decisions the overnight run inferred, replacing an unguided read of what changed."

MoSCoW and Status live in the shared Scope Tracker sheet, and the requirement's phase in `.planning/ROADMAP.md` — **look them up there; this card does not restate them.** The quotes below are the workshop-corpus record.

**Sources:** change record `CR-140` · locus `S-01 26:48`

## What this is for

After an unattended night there is a large amount of changed work and no obvious place to start. Reading it all is not possible and sampling it is guesswork. This requirement replaces that with a review of the judgments the run actually made, on the principle that where the machine had to choose is where it is most likely to have chosen wrong. What it gives the reviewer is a starting point rather than a haystack — in the practitioner's own description, it tells you where to dig instead of making you dig. This is the human half of the delivery loop, and the reason a single person can supervise a night's output at all.

## The evidence

**What the source says.**

> "That was helpful for me because it was like reviewing all of its decisions so I didn't have to dig for it. That became my cues to like where to dig in because it did a stupid thing."
> — the practitioner, `S-01 26:48`–`26:53`

**The reasoning on the register.** **Already built and in use by the practitioner**, and proposed here as a harness capability for the team — so this is porting a working thing, not inventing one. Its value was described exactly: **it tells you where to dig, rather than making you dig.**

**Judgment calls that bear on it.** None recorded against this row on its own.

**RAID rows linked to it.** None directly. The risk that the human reviewer becomes the bottleneck attaches to the ranking rule rather than to this one, but it is the constraint this review exists to answer.

**Glossary terms in play.** *Morning report* — a first-thing-in-the-morning account of what ran overnight. *Overnight mode*. *Cognitive load*.

## Open items and watch-outs

- **This review is only as good as the log it reads.** Its input is a separate requirement, and the two have to agree on a format.
- **It does not scale by itself.** Without the criticality ranking, the review becomes a long list read in whatever order it was written, which is the problem it was meant to solve.
- It is being ported from one person's own loop, which ran on his work rather than on a client delivery. Nothing has yet tested it at team scale.

## Links

- The phase this sits in: `.planning/ROADMAP.md#phase-3-the-morning-opens-on-ranked-decisions`
- Sibling cards: [MORNING100-30](MORNING100-30.md) is the record this reads; [MORNING100-40](MORNING100-40.md) is what makes it survivable at volume; [MORNING100-20](MORNING100-20.md) is the round that opens onto it.
