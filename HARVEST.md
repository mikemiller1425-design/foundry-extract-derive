# Harvest — bee-bootstrap

Planet closed: 2026-09-01.

Do not open `Desktop/Development/bee-bootstrap` to keep building.
Use the slice repos. Open the archive only to copy a named file.

## Archive (on the Mini)

```
~/Desktop/archive/bee-bootstrap-20260901.zip
```

Create it with:

```bash
mkdir -p ~/Desktop/archive
cd ~/Desktop/Development
ditto -c -k --keepParent --norsrc \
  --exclude bee-bootstrap/engine/node_modules \
  --exclude bee-bootstrap/scraper/node_modules \
  --exclude bee-bootstrap/engine/dist \
  bee-bootstrap \
  ~/Desktop/archive/bee-bootstrap-20260901.zip
ls -lh ~/Desktop/archive/bee-bootstrap-20260901.zip
```

Keeps `engine/data/bee-live.db` (the 296 prospects). Drops `node_modules`.

After the zip exists and the size looks sane, move the working tree:

```bash
mv ~/Desktop/Development/bee-bootstrap \
   ~/Desktop/archive/bee-bootstrap-working-copy
```

The Google Drive 24 KB `bee-bootstrap` is not this planet. Leave it or delete it; do not run it.

## Slices (use these)

| Repo | Task | Run |
|---|---|---|
| [biz-by-zip](https://github.com/mikemiller1425-design/biz-by-zip) | ZIP → business list | `./run.sh` (fixture default) |
| [biz-enrich](https://github.com/mikemiller1425-design/biz-enrich) | list → has_website | `./run.sh` |
| [biz-capture](https://github.com/mikemiller1425-design/biz-capture) | URL → snapshot | `./run.sh` |
| [biz-evolver](https://github.com/mikemiller1425-design/biz-evolver) | snapshot → plan | `./run.sh` |
| [biz-preview](https://github.com/mikemiller1425-design/biz-preview) | plan → HTML | `./run.sh` |
| [biz-draft](https://github.com/mikemiller1425-design/biz-draft) | preview → email file | `./run.sh` — does not send |

All live under `~/Documents/GitHub/`.

## Not sliced (stay in the zip)

s08 validation, s10 approval, s11 send, ledger, response, kpi, operator console.

Console, if you must look: `START-CONSOLE.command` inside the archive working copy. Email transport is fake.

## Factory

Loop that produced these slices: `foundry-extract-derive` (`INTENT.md`, `PROCEDURE.md`).
