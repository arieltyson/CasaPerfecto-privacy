# CasaPerfecto Data Mapping

A technical map of every piece of information the site handles, where it lives, and the source file that implements it. Paths refer to [github.com/arieltyson/CasaPerfecto](https://github.com/arieltyson/CasaPerfecto).

## Information you enter

| Data | Stored in | Leaves the device? | Implemented in |
| --- | --- | --- | --- |
| Salary, roommates' salaries, utilities | `sessionStorage`, or `localStorage` on opt-in | No | `src/app/model.ts`, `src/lib/storage.ts` |
| Workplace point | Same as above | No | `src/features/commute/controls.tsx` |
| Commute limit, mode, walking pace | Same as above | No | `src/app/reducer.ts` |
| Must-haves and their values | Same as above | No | `src/features/preferences/PreferencesPanel.tsx` |
| Listings and notes | Same as above | No | `src/features/ledger/ListingForm.tsx` |
| Passphrase | Never stored; the derived key is kept in memory only | No | `src/lib/crypto.ts`, `src/app/state.tsx` |
| Share link contents | The URL fragment you copy | Only if you send the link to someone | `src/lib/share.ts` |

## Encryption

With a passphrase set, saved data is sealed with AES-GCM (256-bit). The key comes from PBKDF2-SHA-256 with 600,000 iterations and a random 16-byte salt, stored next to the ciphertext. See `src/lib/crypto.ts`.

## Network requests

| Request | Destination | Contains your data? |
| --- | --- | --- |
| Page, scripts, styles, fonts | Same origin (GitHub Pages) | No |
| `data/area.json`, `data/places.json`, `data/transit.json`, `data/graph.bin.gz` | Same origin | No |
| `basemap/area.pmtiles` and map fonts and sprites | Same origin | No; byte ranges for the visible map area only |
| Anything else | Blocked by the Content Security Policy (`plugins/csp.ts`) | Not applicable |

`e2e/privacy.spec.ts` fails the build if any request goes to another origin.

## Build-time data

The weekly pipeline (`pipeline/`) downloads public data from OpenStreetMap (Overpass API), AWS Terrain Tiles, DataSF and SFMTA during the build, in GitHub Actions. Your browser never contacts these services.
