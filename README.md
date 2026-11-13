# Bench de Soleil — published data

Generated artifacts for the [Bench de Soleil](https://apps.apple.com/app/id6781811841)
app: a map of Danish public benches by real computed sun and shade.

**This repository is written by an automated export. Do not edit it by hand** —
changes will be overwritten. The source that produces it lives in a separate
private repository.

## What is here

| path | what |
|---|---|
| `manifest.json` | bundle version, horizon encoding, leaf-factor variants |
| `index.json` | per-shard bench counts |
| `overview.json` | per-zoom cluster counts for the low-zoom map tier |
| `tiles/` | bench metadata per map tile |
| `horizons/` | per-bench 360-value sky-obstruction profiles, one byte per degree |
| `weather/` | per-cell hourly cloud-cover forecasts |

The horizon profiles are the interesting part: they describe how much of the sky
each bench can see in every compass direction. That is independent of the date,
so the app computes sun or shade for any moment locally, from geometry, with no
server involved.

## Attribution and licensing

- **Bench, seat and place locations** come from [OpenStreetMap](https://www.openstreetmap.org/),
  © OpenStreetMap contributors, available under the
  [Open Database License](https://opendatacommons.org/licenses/odbl/). Data
  derived from it here is likewise ODbL.
- **Buildings, terrain and canopy** derive from Danish public data
  ([Datafordeler](https://datafordeler.dk/) — GeoDanmark and DHM), used under
  their open-data terms.
- **Cloud-cover forecasts** come from the
  [Norwegian Meteorological Institute](https://api.met.no/) (MET Norway),
  licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) /
  [NLOD](https://data.norge.no/nlod/en/2.0).

## Privacy

Nothing here is user data. These files are a static publish of public
geographic and weather data; the app reads them the way it would read any
static file, and no request from a user's device reaches the upstream sources.
