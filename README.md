# juggle

> ## ⚠️ Retired — superseded by the web app
>
> This CLI is **deprecated as of 2026-08-02** and no longer maintained. It was
> rewritten as a web app — **[juggle-web](https://github.com/Alienchisel/juggle-web)** —
> now the canonical tracker, running as a Slipway berth at `yard:4102`.
>
> - All history was migrated and **parity-verified** (3182 trials, Apex 376) against this repo.
> - Backups are automated and off-box (`juggle-web` → `juggle-data`).
> - **Do not log new trials here.** This repo's `juggle-data/` is now a frozen
>   snapshot; the web app's database is the single source of truth.
>
> The notes below describe the retired CLI, kept for reference.

Personal 3-ball juggling score tracker for the terminal. Logs trials, tracks personal bests, computes streaks and trends, and unlocks a "Codex" of discoveries over time.

## Requirements

- `bash`
- GNU `date` (`date -d` must work)
- [`gum`](https://github.com/charmbracelet/gum) — TUI toolkit (hard dependency)
- `flock` — optional, used for atomic write protection

## Setup

```sh
git clone <this repo>
cd juggle
chmod +x juggle
./juggle --help
```

Optionally put it on your `$PATH`:

```sh
ln -s "$PWD/juggle" ~/.local/bin/juggle
```

## Usage

```
juggle <number>    log a trial (e.g. juggle 20)
juggle stats       the Reckoning — Apex, Auguries, Titles, charts
juggle trend       weekly/monthly trends + sparkline
juggle day|week|month|year [date]   recap windows
juggle codex       permanent discoveries & achievements
juggle lore        all systems explained
juggle backup      snapshot juggle-data/ to a timestamped backup
juggle doctor      validate data & registry integrity
juggle --help      full command list
```

## Data

Data lives in `./juggle-data/` next to the script; backups go in `./juggle-backups/`. Both are git-ignored. Override the locations with:

```sh
JUGGLE_DATA_DIR=/path/to/data
JUGGLE_BACKUP_DIR=/path/to/backups
```
