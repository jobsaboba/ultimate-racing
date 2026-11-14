# Ultimate Racing

Hot trainer + hot jockey + a fit, short-priced horse — as a PWA.

**The rule** (all stats walk-forward — only the 14 days before the day count,
computed over **all British and Irish racing**, not just the Grail's races):

- trainer: **3+ wins in the last 14 days at 50%+ strike rate**
- jockey: **the same** — 3+ wins, 50%+ strike
- horse: **ran in the last 14 days**
- horse: **top 5 in the betting odds**

**The money:** £10 bank, the day's selections run as a **full perm** —
n selections = n singles + every double + treble + … + one n-fold —
each line staking **1% of the rolling bank**. Placed at its first leg's
off, win-only at the published odds, a line pays only when every leg wins.
Non-runners and void races refund. Staking defaults are one line in
`ultimate_racing.py` (`START_BANK`, `STAKE_PCT`) if they ever need changing.

- Live app: https://jobsaboba.github.io/ultimate-racing/
- Data: `data/<date>.json` (picks + every settled perm line at actual stake)
  + `data/stats.json` + `data/index.json` + `data/latest.json`

## Publish

The full-racing store (every GB/IE race since 1 Jan, from Sporting Life)
is built by `ult_backfill.py` — resumable, cached. Then:

    python3 ~/racing-scripts/ult_backfill.py      # catch the store up
    python3 ~/racing-scripts/ultimate_racing.py --publish

Runs at 06:55 every morning (after the Grail's 06:00) and on the half-hour
settle tick from `results-refresh.sh`.

## App

Two views: **The day** (day tabs along the top, bank card, day
staked/return/P/L, then every line grouped by fold size with legs, form
chips, badges and returns) and **The run** (season totals, by-fold table,
monthly P/L, best day, the rule). Blues and greys, horse icon, installable.
Service worker cache: `ult-v1` — bump it and the version whenever
`index.html` changes.

## Local repos

    ~/projects/ultimate-racing          ← this repo (main → GitHub Pages)
    ~/racing-scripts/ultimate_racing.py ← the engine
    ~/racing-scripts/ult_backfill.py    ← the full-racing store builder
    ~/racing-scripts/ult_store/         ← every GB/IE race since 1 Jan

Commits use identity `jobsaboba <160133851+jobsaboba@users.noreply.github.com>`.
