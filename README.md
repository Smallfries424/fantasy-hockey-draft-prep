# Fantasy Hockey Draft Prep (2026-27)

A small draft-day toolkit for redraft fantasy hockey: an interactive draft board plus notes digested from the DFO Fantasy Show's positional preview episodes and DailyFaceoff's player projections.

**Live draft board:** enable GitHub Pages on this repo (Settings → Pages → Deploy from branch → `main` / `docs`) or just open [`docs/index.html`](docs/index.html) locally in a browser — no build step, no dependencies.

## What's in here

- **`docs/index.html` + `docs/players.json`** — the interactive draft board. Static HTML/JS, reads `players.json` for its player pool (rank, position, team, projected stats, fantasy points, ADP). Sortable/filterable at the browser level, no server needed.
- **`draft-rankings.md`** — a 298-player board re-sorted by custom fantasy-points-per-league-scoring math (4 pts/goal, 2.5/assist, 1/PPP, 0.4/SOG, 0.5/hit, 0.6/block for skaters; 4/win, -1/loss, -0.5/GA, 0.25/save, 5/shutout for goalies) instead of generic ADP. Built from DailyFaceoff's Brock Seguin 1-300 player profile projections. Known limitations are called out at the top of the file (no shorthanded-point data, approximated goalie losses/GA).
- **`positional-preview-digest.md`** — top-10 consensus rankings, value picks, breakouts, and "ADP to avoid" calls by position (center, LW, RW, D), digested from the DFO Fantasy Show podcast's positional preview episodes.

## Adapting this for your own league

`players.json` is a flat array of player objects (`rank`, `name`, `posGroup`, `pos`, `team`, `fpts`, `adp`, `isGoalie`, `stats: {g, a, ppp, sog, hit, blk}`, plus `newRank`/`delta` for ranking-shift columns). Swap in your own projections and scoring weights to regenerate `fpts`/`newRank`, and the board in `docs/index.html` will just work against the new data — it doesn't hardcode any player names.

## Sources & attribution

- Player projections underlying `players.json` and `draft-rankings.md` are derived from [DailyFaceoff's 2026-27 fantasy hockey player profiles](https://www.dailyfaceoff.com/news/brock-seguins-fantasy-hockey-player-profiles-1-100-2026-27) (Brock Seguin).
- Positional analysis in `positional-preview-digest.md` is summarized from the DFO Fantasy Show podcast's 2026-27 positional preview episodes (hosts Brock Seguin and Bibbs Bondi).
- This repo contains original commentary/summaries and a derived numeric dataset, not verbatim reproductions of the source articles or podcast transcripts.

## License

Code (`docs/`) is MIT-licensed — see [LICENSE](LICENSE). The notes and derived rankings are original analysis, free to reuse or adapt; please keep the source attribution above when redistributing.
