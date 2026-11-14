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

**The season walk (1 Jan → now, all GB/IE racing from Sporting Life):**
the rule fired on just **13 days — 16 selections → 19 perm lines ·
10 won · 9 lost · 53% strike** · £1.93 staked → £2.16 · bank **£10 → £10.23**
· ROI +11.9%. It's a rare-bird rule: hot trainer *and* hot jockey in the
top five almost never coincide — 11 singles (+16.7% ROI, incl. Beorma 8/11
and 4/11, Gore Point 1/2, Sunray Shadow 8/15) and 3 doubles (1 won).
Best day 4 Nov (Carrigans Grove 11/8 Dundalk). Monthly: only April (−10p)
and September (−16p) red.

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
