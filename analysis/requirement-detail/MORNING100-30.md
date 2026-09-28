---
id: MORNING100-30
tracker_id: MORNING100.30
title: "Log every inference"
---

# MORNING100-30 — Log every inference

> "An unattended run logs every decision it inferred, or would have asked about, with the reason it chose as it did and how to reverse it."

MoSCoW and Status live in the shared Scope Tracker sheet, and the requirement's phase in `.planning/ROADMAP.md` — **look them up there; this card does not restate them.** The quotes below are the workshop-corpus record.

**Sources:** change record `CR-160` · locus `S-01 26:15`

## What this is for

When nobody is present, every question the run would have asked gets answered by the run itself, and those answers are invisible afterwards. This requirement makes them visible, and it insists on two things beyond the decision: why it was chosen, and how to undo it. Those two are what turn a log into something a reviewer can act on — without the reversal, a reader who disagrees with an entry has no move available but to raise it and wait. It is the record the whole morning review reads, and the single most load-bearing artifact the night produces.

## The evidence

**What the source says.**

> "But what I built was I had an interactive mode and I had an overnight mode. And so when I kicked it into overnight mode, I instructed the orchestrator to log every decision it had to infer or would have wanted to ask me. And so then when I flipped it to morning mode, it reviewed with me and I had to do one by one. Here, here's an inference I made as I was going forward. Here's why I did it. If you disagree, here's how we back out of it."
> — the practitioner, `S-01 26:10`–`26:36`

**This is the most load-bearing quotation in the phase.** It carries the log, the reason, the reversal, the one-at-a-time review and the mode transition in one passage, and four requirements derive from it.

**The reasoning on the register.** The record the morning review reads. **Reason and reversal are both required: a decision without its reversal is a decision the reviewer cannot act on.**

**Judgment calls that bear on it.** The row was read against the question *does it produce an artifact whose contents the practitioner would pick?* and left silent on interactivity, for a stated reason: **it is written by a process as it runs, unattended, so there is no moment at which a human picks its contents.**

**RAID rows linked to it.** None. No row on the RAID sheet links this requirement.

**Glossary terms in play.** *Overnight mode*. *Morning report*. *Cognitive load*.

## Open items and watch-outs

- **The log is written by the dispatch round and read by the review round, so it spans two phases and its format is a contract between them**, not a detail inside either.
- **Some inferred decisions may have no clean reversal.** If so, the entry has to say that rather than being left out, or the log quietly becomes a list of the reversible half.
- Nothing here has been tested at delivery scale. The practitioner's own loop is the evidence, and it ran on his work.

## Links

- The phase this sits in: `.planning/ROADMAP.md#phase-3-the-morning-opens-on-ranked-decisions`
- Sibling cards: [NIGHT100-10](NIGHT100-10.md) is the run that writes this record; [MORNING100-10](MORNING100-10.md) is the review that reads it; [MORNING100-40](MORNING100-40.md) orders it.
