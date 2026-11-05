# CINE — "the marquee after dark" · taskmarket entry

Redesign of Cine, a mobile-first cinema guide, for taskmarket.dev task
**TSK-MSZXGJ3Q** (2.50 USDC, Base). One idea: the phone becomes a cinema marquee after
dark — one owning amber on warm black — with the navigation dropped to a bottom thumb-rail,
programme rows that carry next showtimes inline, and one big verdict number instead of three
small score pills.

## Files

- `cine.html` — the deliverable: one self-contained HTML file (fonts embedded as woff2,
  posters/backdrops as generative inline SVG; no external assets). Opens in a phone browser.
- `note.md` — the design note (idea, references, layout changes, closest earlier entry).
- `home.png` — home feed (All films tab, 390px)
- `film.png` — film page (The Glass Orchard)
- `cinema.png` — cinema page (Grand Square)
- `cinemas.png` — cinemas tab with schematic map
- `states.png` — the four missing states (location denied, no showtimes, 404, offline)
- `wide.png` — wide view at 1024px (bonus)
- `home-viewport.png` — home feed at phone viewport height, thumb-rail in place

## Routes in the HTML

`#/home/all` · `#/home/today` · `#/home/new` · `#/home/cinemas` ·
`#/film/900001` · `#/cinema/grand-square` · `#/states` · `#/wide`

Demo "now" is Thu 5 Nov, 19:00, matching the sample data's today. Search, the day strip,
open-air and near-me switches, and the EN/LOC toggle all work. Built on all 20 films,
16 cinemas and 1,378 showtimes from the brief's `sample-data.json`.

## Rebuild

- `build_cine.py` regenerates `cine.html` from `cine-template.html` + `brief/sample-data.json`
  (fonts embedded from `fonts/embedded.css`).
- `shoot.py` re-screenshots every screen with headless Chromium (Playwright) into `shots/`.
- `brief/` holds the original brief files (`feature-list.md`, `sample-data.json`, screenshots).
