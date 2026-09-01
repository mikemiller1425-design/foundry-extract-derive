# Slice queue (from bee-bootstrap)

## Runnable fixture CLIs
- biz-by-zip — ZIP → list
- biz-enrich — list → has_website
- biz-capture — URL → snapshot (no live write)
- biz-evolver — snapshot → plan JSON (no live LLM)
- biz-preview — plan → static HTML (not the live site)
- biz-draft — preview → email file (sent=0)

## Stay in the pile
- s08 validation, s10 approval, s11 send, ledger, response, kpi, console
