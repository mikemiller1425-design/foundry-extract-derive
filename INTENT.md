# foundry-extract-derive — FROZEN v0.1

This folder turns a partial or failed planet into **one derived SPEC**.
It does not run the planet. Conductor only sees a file you copy.

## Words (frozen)

- **Planet** — real project folder (`bee-bootstrap/engine`)
- **Law** — governing doc (`MASTER_BUILD_SPEC.md`)
- **Stage** — named folder already on disk
- **Milestone** — a “done when” line in the law
- **Extract** — name planet + law, list stages, pick first observable milestone, KEEP / REPAIR / OUT
- **Derive** — write one SPEC by binding only the law that protects that milestone
- **Derived SPEC** — only export
- **Handoff** — copy SPEC → Foundry `SPEC.md` → `foundry-advance spec` → `foundry-conductor/tasks/*.json`

Forbidden words here: blend, recipe, tasks-for-planets.

## Tree (frozen)

```
foundry-extract-derive/
  INTENT.md
  PROCEDURE.md
  inbox/
  work/<ticket-id>/{PLANET,STAGES,CUT}.md
  out/<ticket-id>/SPEC.md
  logs/
```

## Hard rules (frozen)

- No second copy of an engine under inbox
- `out/` is SPEC files only
- Conductor `tasks/` is JSON only
- This folder never calls Places, SMTP, NAS, or Foundry
- One ticket at a time until accepted

## First ticket (already derived — do not re-derive)

`out/biz_by_zip/SPEC.md`
