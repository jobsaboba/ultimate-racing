# Ultimate Racing

The points machine — every 8+-runner race scored out of **55**, Dave's own system.

**The points:**

| Rule | Points |
|---|---|
| Stars — Timeform ★ + Racing Post ★ (max 5 + 5) | up to **10** |
| Favouritism (forecast) — 1st / 2nd / 3rd / 4th fav | **10 / 7 / 5 / 3** |
| Course form — C&D winner / distance winner / course winner | **10 / 5 / 3** |
| Jockey — 3+ wins last 7 days (else 3+ wins last 14) | **5** (else **3**) |
| Trainer — 3+ wins last 7 days (else 3+ wins last 14) | **5** (else **3**) |
| Top course trainer among today's runners (course win %) | **5 / 4 / 3 / 2 / 1** |
| Top course jockey among today's runners (course win %) | **5 / 4 / 3 / 2 / 1** |
| Trainer in flat-stake profit over the last 14 days | **5** |

Racing Post stars come from their RPR ranks (highest RPR = 5★ …) — their own
stars are Pro-gated. At The Races is not used. Jockey/trainer win counts and
the profit check are computed from the book's own settled sheets.

**The bank:** £10 start — **every race's top-panel horse priced 3/1–10/1** is
backed **win-only** at the published odds (non-runners refund, the bank rolls
forward), staked by a **Jacobs ladder**: 1% of the day's balance a bet at
rung 1 — a losing day climbs 1·2·2·3·4·5…, a winning day resets to 1. The band
is the backfill's verdict: top horses priced odds-on lost −31% over the season,
3/1–10/1 made +17.8%. Each-way at 365 place terms was tested on the same bets
and lost (+7.8% vs +15.2%). Every horse's finishing position is in the day
files — the app colours winners green, placed (2nd/3rd) orange, losers red.
The bank card has a bank box that sizes today's stake for your own bank; the
app's "The run" tab shows the walk.

*(This app previously hosted the hot-trainer perm system — retired 17 Nov 2026.
Its day files live on in this repo's git history.)*

- Live app: https://jobsaboba.github.io/ultimate-racing/
- Data: `data/<date>.json` (races, runners, full points breakdown per horse)
- Publisher: `~/racing-scripts/ultimate_racing.py` — runs at 05:55 from
  `ultimate-morning.sh` (waits for the 05:30 ratings collect) and again with
  the afternoon settles via `results-refresh.sh`.
