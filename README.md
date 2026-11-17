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

*(This app previously hosted the hot-trainer perm system — retired 17 Nov 2026.
Its day files live on in this repo's git history.)*

- Live app: https://jobsaboba.github.io/ultimate-racing/
- Data: `data/<date>.json` (races, runners, full points breakdown per horse)
- Publisher: `~/racing-scripts/ultimate_racing.py` — runs at 05:55 from
  `ultimate-morning.sh` (waits for the 05:30 ratings collect) and again with
  the afternoon settles via `results-refresh.sh`.
