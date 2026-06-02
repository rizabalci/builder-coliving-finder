# Builder Coliving Finder

An interactive, client-side finder for builder residencies, founder houses, and
remote-work coliving worldwide. Filter by cost per person, program type, region,
visa reality, stay length, and whether outside work is allowed. View results as
cards or on a date timeline, and star favourites.

**Live site:** https://rizabalci.github.io/builder-coliving-finder/

## Features

- Search by name, city, or country
- Filter by program type (structured residency vs open coliving), region, max
  budget per person, visa difficulty, and "allows outside work"
- Cost breakdown per person per month, with a total for your chosen stay length
- Sharing toggle that halves per-room pricing when splitting a room
- Cards view and a Dates timeline (fixed-date residencies vs rolling coliving)
- Favourites that persist in your browser
- Visa ratings scored for a Turkish passport + Slovak/Schengen residence
- Fully client-side: no API, no keys, no tracking, no external scripts or fonts

## How it works

`index.html` is the whole app. All program data lives in a single `PROGRAMS`
array near the top of the `<script>` block, marked `DATA BLOCK`. The page reads
that array and renders everything. Region filter chips are generated
automatically from whatever regions appear in the data.

## Updating the data

The data block is the only thing you edit. Each entry looks like:

```js
{name:"Network School", type:"A", region:"SE Asia", city:"Forest City",
 country:"Malaysia", monthly:1400, priceBasis:"per_person", outsideWork:true,
 visa:"easy", visaNote:"...", start:null, weeks:null, wifi:"Fast",
 tz:"MYT (GMT+8)", apply:"https://ns.com/"}
```

Field guide:

- `type` — `"A"` structured residency/cohort, `"B"` open coliving
- `region` — free text; becomes a filter chip automatically
- `priceBasis` — `"per_person"` or `"per_room"` (sharing splits per_room only)
- `monthly` — EUR, all-in, approximate; confirm on the program's site
- `outsideWork` — `true` if you can keep your own remote work/income
- `visa` — `"easy"` / `"medium"` / `"hard"`
- `visaNote` — short reality check; verify against the official source
- `start` / `weeks` — `"YYYY-MM-DD"` plus length for type A; `null` for rolling B
- `wifi` / `tz` / `apply` — note, timezone label, real application URL

To refresh: run the research prompt (see the prompt files in this repo), then
paste verified entries into the `PROGRAMS` array, commit, and push.

## Notes on the current data

The data comes in two clearly separated tiers, gathered by web research with
verified visa ratings as of mid-2026.

1. **Direct-link tier (41 entries):** named operators, residencies and travel
   programs whose `apply` link points straight at that operator's own site,
   e.g. Anceu Coliving, Cloud Citadel, Outsite, Sun and Co., Network School.
   These are the "Travel & work programs" and "Places to live" sections.
2. **Browse-by-city tier (170 entries):** whole-city scenes (Lisbon, Tokyo,
   Medellín, etc.) shown in their own "Browse by city" section. Each links a
   real coliving directory for that city rather than naming one house, because
   a city has dozens of operators that turn over fast. These are labelled
   "City · browse" and kept apart from the direct-link tier so it is always
   obvious which is which. Filter to just these with the "Browse by city" chip.

Prices and cohort dates change often, so the `apply` link is always the source
of truth.

## Deploy

GitHub Pages serves `index.html` over `README.md` automatically. Push
`index.html` to the repo root on the `main` branch and the live site updates
within a minute or two.

## License

MIT
