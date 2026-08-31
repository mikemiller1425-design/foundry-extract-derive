# SPEC — biz_by_zip

**Ticket id:** `biz_by_zip`  
**Planet:** `~/Desktop/Development/bee-bootstrap/engine`  
**Law:** `docs/MASTER_BUILD_SPEC.md` M1 only (targeting + discovery + dedupe)  
**Workflow:** `generic_dag`  
**One job:** take a ZIP code, return the businesses registered to that ZIP.

## Outcome

Operator supplies one US 5-digit ZIP.  
System returns a deduplicated list of businesses for that ZIP, each with a stable `biz_<ULID>` and `lifecycle_state = DISCOVERED`.

That list is the product. Nothing else.

## Input

- One ZIP string
- Fixture discovery provider (no live Google Places in this ticket)

## Allowed paths

- `src/stages/s01_targeting/**`
- `src/stages/s02_discovery/**`
- `src/stages/s03_dedupe/**`
- `src/providers/discovery/**`
- existing tests/fixtures for those four trees only

## Stages allowed in the task JSON

Declare only stages that already exist in those folders, plus at most one `test` stage whose command runs the existing M1 / discovery / dedupe tests.

Do not invent stages.  
Do not declare `repair-m1-slice`, `verify-m1-tests`, or any name that is not a real folder or a single test gate.  
If a test stage exists, its `dependsOn` must be stages that are also declared in the same file.

## Must not

- Live Google Places
- Enrichment, `has_website`, capture, evolver, preview, email, send
- Foundry imports
- NAS, Make, SMTP
- New product behavior beyond ZIP → business list
- Live engine checkout as cwd

## Acceptance

1. Fixture ZIP in → business rows out, unique `biz_` ids.
2. Same ZIP again → no new duplicate active businesses.
3. Existing targeting / discovery / dedupe tests pass. Do not add a new test framework.
4. Task JSON names only declared stages. Doctor must accept it.

## Handoff

Accepted artifact: the `DISCOVERED` business list for one ZIP.  
Analyzer is a later ticket. Not this one.
