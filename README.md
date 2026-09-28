# Handover — a plan for changing the requirements harness itself

This package holds a plan, not code. A delivery pod pointed its own requirements harness at a
recording of its own working session and produced a roadmap for changing that harness. Nothing here
has touched the harness's code yet; the package stops where the build begins.

## What is here

- `.planning/ROADMAP.md` — eight phases in dependency order, each with its goal, its success
  criteria and the decisions it must close. This is the phase view.
- `.planning/REQUIREMENTS.md` — the 24 requirements, and the table that maps each one to its phase
  and to the change record it came from.
- `.planning/PROJECT.md` and `.planning/STATE.md` — what the project is, the decisions taken while
  planning, and where the work stands.
- `analysis/requirement-detail/` — one card per requirement, with an index that lists them by
  family. **A requirement's reasoning lives on its card, not in the roadmap:** the source quotation,
  the judgment calls, the open items. Read the card before planning the requirement.
- **The raw sources every quotation points into are NOT in this archive.** They are published on
  the handover site under "The sources", at `workshop-docs/<name>`. Every locus in a card and in
  the roadmap names a path there; those pointers are correct about where the material lives, and
  following one needs the site rather than this download.

## The one instruction

Copy `.planning/` and `analysis/` into the repository the work will be built in, then run
`/gsd-plan-phase 1` — or `/gsd-next`, which reads the state and routes to it. **Those two
directories are the whole archive besides this file**; the raw sources are read on the site, not
copied, so keep the site reachable while the requirements are being planned.

**Do not run `/gsd-new-milestone`.** It is the natural guess. It creates or updates the requirements
and roadmap files, so on this package it regenerates both and discards everything the engagement
produced. If it has already run, restore both files from this package before going further.

## Two kinds of identifier

`CR-010` to `CR-270` are the business's record of what was agreed; they belong to the change
register the pod keeps. `NIGHT100-30` and its kind are the delivery identifiers the roadmap, the
cards and the site use. The mapping between them is written in `.planning/REQUIREMENTS.md`'s
traceability table and on each card's Sources line. Do not renumber either kind.

## What is not here

MoSCoW ratings and status live in the shared Scope Tracker sheet the site links to, and no file
here restates a MoSCoW rating. **One file restates status:** `.planning/REQUIREMENTS.md`'s
traceability table carries a `Status` column, every row reading `Pending`, which records that no
phase has been planned yet rather than tracking the sheet. Read the sheet for the live value.
There are no phase plans and no estimates — phase planning is the receiving team's first act, not
this package's last.
