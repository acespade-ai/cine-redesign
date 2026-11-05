# CINE — redesign note

## The idea

CINE as a cinema marquee after dark: one owning amber on warm black, so the app reads as a
place that shows films, not a list that manages them. The feed becomes a programme — tonight's
films as full-bleed rows with the next showtimes inline — and the navigation drops to the thumb.

References: the marquee and now-showing boards of independent cinemas; Citymapper's thumb-first
bottom bar and day strip; Letterboxd's verdict-first scores; festival-programme grids
(Berlinale schedule pages) for the wide view.

## What moved, merged or changed — and why

- **Four top tabs → a fixed bottom thumb-rail** (Tonight / New / All films / Cinemas). The
  feed is what you scroll; the nav belongs where your thumb already is. Search stays sticky
  under the header; the wordmark + language pill stay on top.
- **A date strip (Thu 5 – Wed 11) sits under the toolbar.** "Tonight" becomes a day you
  pick, not a tab you hunt — the same strip drives which showtimes each row shows.
- **Film cards → full-bleed programme rows.** Backdrop band + huge condensed title +
  one verdict number + the next three times + "N cinemas · M screens" in a single row, so
  "what can I see tonight, where, and is it any good?" is answered without opening the film.
- **Three score pills → one verdict.** The best available score goes big with its source
  (IMDb / RT / MC); the other two stay small beside it. Every grade also carries a word —
  GREAT / GOOD / MEH — so it reads without colour. Films with no scores get an explicit
  "No scores yet — be the first to judge" line (Kids of the Overpass has none at all;
  Saltwater Saints has IMDb only).
- **Mascot pick → an amber ticket stub** (perforated edges, "CINE SAYS", signature). The
  ratings legend keeps the three sample chips + colour key.
- **Cinemas tab is list-first.** Neighbourhood sections in geographic order, cinema rows
  with format chips and the open-air sun; a schematic SVG map on top (real lat/lng from the
  data, pins carry today's film count, amber for open-air) instead of a tile map, so the
  single file stays self-contained. Cinema pages now show the phone, website and address the
  data already has but the app hides.
- **Film page:** poster + title + all three score chips, mascot synopsis when present,
  showtimes grouped by area with day rows, the next show highlighted in amber, format and
  DUB tags on time chips, and tickets as one full-width amber button per cinema.
- **The four missing states are designed, not left blank:** location denied (banner + keep
  browsing by area), film with no showtimes, 404, offline (last good copy with timestamp).
- **Posters and backdrops are generative SVG art** (deterministic per film: hue + motif from
  the film id). The brief's placeholders are low-res and the single file must open on its
  own; type is embedded woff2 (Anton / Inter / IBM Plex Mono), so the file renders
  identically offline. No other external assets.
- **Wide view (bonus):** the feed grows into a three-across programme grid and the map docks
  beside the list. Same order, same thumb-first logic — nothing re-learned.
- **Language:** the EN/LOC toggle is wired end to end (labels, rail, placeholders). Two
  honest limits: the sample data ships no local-language strings, so the local chrome uses
  placeholder translations and local film/cinema names match English in the data; and the data
  carries no verified/second-hand flag, so no verified tick is shown rather than an invented
  one. The city is called "the Capital" — the brief's unnamed capital.

## Closest earlier entry — and how this differs

I reviewed the public submission list before building (21 entries at the time; most are one
HTML file + a note, several add the missing-state screens as extra PNGs). The closest in
format is the most recent entry, **ZeroNebulaCrystal (SUB-EEX9PE47)** — a single HTML file
with a note, in the same required shape. I could not inspect its rendered design (the
public listing shows the file list, not the design), so the difference I can state is
structural: mine is the only entry I saw framed around a dark marquee system with the
navigation moved to a bottom thumb-rail, verdict-first scoring, and programme rows that
carry next showtimes inline — the rest of the field, as listed, keeps the current app's
light theme and top-tab structure.

## How to open

Open `cine.html` in a phone browser (390px). Routes: `#/home/all` (feed),
`#/home/today`, `#/home/new`, `#/home/cinemas`, `#/film/900001` (The Glass Orchard),
`#/cinema/grand-square`, `#/states`, `#/wide`. Demo "now" is Thu 5 Nov, 19:00, so
"tonight" and next-show highlights match the sample data's today. All 20 films, 16
cinemas and 1,378 showtimes from `sample-data.json` are embedded; search, day strip,
open-air and near-me switches, and the language toggle all work.
