# Requirement detail — one card per requirement on the roadmap

This directory holds one card per requirement the board renders. **The set is the 24 requirements
on the roadmap's phase tables**, and the count follows from that rule rather than the other way
round. **The change register has since moved ahead of the roadmap and carries 27 rows**, so three
of them have no card here yet; the paragraph on namespaces below says which and why. Each card
carries the requirement's verbatim statement, what the requirement is for, the
evidence behind it, the open items, and links to the phase it sits in and the sibling cards it
depends on. **Presence in this index means the board shows the requirement, never that the business
has agreed it.**

**Two identifier namespaces, and a mapping between them.** The change register owns `CR-010` to
`CR-270` — the business's namespace, what was agreed, in the language of the approval, and it does
not move. These cards, the roadmap and `.planning/REQUIREMENTS.md` own family identifiers, the
delivery namespace the site renders and the navigation groups by. **Between them is a mapping, not
an equivalence:** one change record may become two delivery items, or two collapse into one. For
this milestone the mapping is one-to-one across 24 of the register's 27 rows. **The three that map
to nothing are `CR-250`, `CR-260` and `CR-270`, and their `Delivery ID` column is deliberately
empty rather than incomplete:** all three are subtractions — they delete a round, a kit and a
stage — and a subtraction takes a delivery identifier only when a roadmap phase adopts it. They
are awaiting that phase, not missing a card. Every card names its origin change record on its
`Sources:` line; every register row that became a delivery item names what it became, in its
`Delivery ID` column; and `.planning/REQUIREMENTS.md`'s traceability table carries both together.

**Cards carry evidence, not live values.** MoSCoW and Status live in the business's shared Scope
Tracker sheet, and a requirement's phase lives in `.planning/ROADMAP.md`. **Look those up at the
source — no card restates them**, so an edit to the sheet or the roadmap never leaves a card stale.
What a card quotes — the requirement statement, the source passage, the reasoning and the judgment
calls — is the workshop-corpus record behind the row.

**Reading order when planning a requirement:** read the card here first; then follow its locus into
`workshop-docs/` for the verbatim source passage, where an `S-01` reference is a timestamp in the
working-session transcript and an `S-02` reference is a dated heading in the practitioner's notes;
then `.planning/REQUIREMENTS.md`'s traceability table for the change record the requirement came
from, and `.planning/ROADMAP.md` for the phase it sits in. **This paragraph is here rather than in the front door** because an agent
planning a requirement meets the reading order in the layer it is already standing in, rather than
in a document it may never open.

## Front-matter contract

Every card opens with YAML front matter using exactly these keys — identity only. A consumer that
needs ratings, status or the phase joins on `tracker_id` against the live sheet, or on `id` against
the roadmap's traceability table.

| Key | Type | Meaning |
|---|---|---|
| `id` | string | The planning-document identifier, with the final dot written as a hyphen (`NIGHT100-10`) |
| `tracker_id` | string | The same identifier in the tracker's own dot form (`NIGHT100.10`) — the join key against the live sheet |
| `title` | string | Short name, taken from the requirement's line in `.planning/REQUIREMENTS.md` |

## The 24 cards, by family

**CAPTURE — Workshop capture**
- [CAPTURE100-10](CAPTURE100-10.md) — Feed the session live

**SITE — The handover site and the tracker it renders**
- [SITE100-10](SITE100-10.md) — Generate the tracker
- [SITE100-20](SITE100-20.md) — Clean the content pages
- [SITE100-30](SITE100-30.md) — Add progressive reveal
- [SITE100-40](SITE100-40.md) — Mark each content area

**KIT — The documentation kit**
- [KIT100-10](KIT100-10.md) — Return the review's feedback
- [KIT100-20](KIT100-20.md) — Drop the signature record

**PLAN — Planning and roadmap**
- [PLAN100-10](PLAN100-10.md) — Execute the agreed requirements

**NIGHT — The unattended run**
- [NIGHT100-10](NIGHT100-10.md) — Dispatch at day's end
- [NIGHT100-20](NIGHT100-20.md) — Enter overnight mode
- [NIGHT100-30](NIGHT100-30.md) — Run the verification loop
- [NIGHT100-40](NIGHT100-40.md) — Stop on a broken gate
- [NIGHT100-50](NIGHT100-50.md) — Bound the automation

**MORNING — The morning review**
- [MORNING100-10](MORNING100-10.md) — Open with the decisions
- [MORNING100-20](MORNING100-20.md) — Leave the run for morning mode
- [MORNING100-30](MORNING100-30.md) — Log every inference
- [MORNING100-40](MORNING100-40.md) — Rank by criticality
- [MORNING100-50](MORNING100-50.md) — Capture the lessons
- [MORNING100-60](MORNING100-60.md) — Log the problems

**DEMO — The daily session pack**
- [DEMO100-10](DEMO100-10.md) — Generate the session pack
- [DEMO100-20](DEMO100-20.md) — Demonstrate the overnight build
- [DEMO100-30](DEMO100-30.md) — Propose what comes next
- [DEMO100-40](DEMO100-40.md) — Hand over for UAT

**REPORT — Reporting and handover**
- [REPORT100-10](REPORT100-10.md) — Generate the weekly status report
