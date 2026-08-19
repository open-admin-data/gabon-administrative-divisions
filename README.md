# Gabon Administrative Divisions / Gabon



## Overview

| Item | Details |
|------|---------|
| Province | 9 |
| Department | 48 |
| Settlement | 4,192 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/ga](https://openadmindata.org/ga/) |
| API | [openadmindata.org/api/ga](https://openadmindata.org/api/ga/) |
| National Anthem | [🎵 Listen & Download Gabon National Anthem MP3](https://onlygames.me/national-anthems/ga/) |

## Browse by Province

| # | Province | Departments | Settlements | Link |
|---|----|----|----|------|
| 1 | Nyanga | 6 | 389 | [Browse](divisions/nyanga/) |
| 2 | Ngounie | 9 | 816 | [Browse](divisions/ngounie/) |
| 3 | Ogooue-Maritime | 3 | 261 | [Browse](divisions/ogooue-maritime/) |
| 4 | Haut-Ogooue | 11 | 364 | [Browse](divisions/haut-ogooue/) |
| 5 | Moyen-Ogooue | 2 | 306 | [Browse](divisions/moyen-ogooue/) |
| 6 | Ogooue-Lolo | 4 | 438 | [Browse](divisions/ogooue-lolo/) |
| 7 | Estuaire | 4 | 478 | [Browse](divisions/estuaire/) |
| 8 | Ogooue-Ivindo | 4 | 350 | [Browse](divisions/ogooue-ivindo/) |
| 9 | Woleu-Ntem | 5 | 790 | [Browse](divisions/woleu-ntem/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 9 province records |
| [all-department.json](data/all-department.json) | JSON | All 48 department records |
| [all-settlement.json](data/all-settlement.json) | JSON | All 4,192 settlement records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['department']} departments")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=department, 3=settlement |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
divisions/{province-slug}/{department-slug}/
```

Settlements are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Gabon Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/gabon-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
