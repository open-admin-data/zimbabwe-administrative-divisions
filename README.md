# Zimbabwe Administrative Divisions / Zimbabwe



## Overview

| Item | Details |
|------|---------|
| Province | 10 |
| District | 91 |
| Ward | 1,961 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-28 |
| Website | [openadmindata.org/zw](https://openadmindata.org/zw/) |
| API | [openadmindata.org/api/zw](https://openadmindata.org/api/zw/) |

## Browse by Province

| # | Province | Districts | Wards | Link |
|---|----|----|----|------|
| 1 | Bulawayo | 1 | 29 | [Browse](divisions/bulawayo-zw10/) |
| 2 | Harare | 4 | 78 | [Browse](divisions/harare-zw19/) |
| 3 | Manicaland | 10 | 260 | [Browse](divisions/manicaland-zw11/) |
| 4 | Mashonaland Central | 10 | 232 | [Browse](divisions/mashonaland-central-zw12/) |
| 5 | Mashonaland East | 11 | 229 | [Browse](divisions/mashonaland-east-zw13/) |
| 6 | Mashonaland West | 13 | 231 | [Browse](divisions/mashonaland-west-zw14/) |
| 7 | Masvingo | 9 | 243 | [Browse](divisions/masvingo-zw18/) |
| 8 | Matabeleland North | 9 | 193 | [Browse](divisions/matabeleland-north-zw15/) |
| 9 | Matabeleland South | 10 | 170 | [Browse](divisions/matabeleland-south-zw16/) |
| 10 | Midlands | 14 | 296 | [Browse](divisions/midlands-zw17/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 10 province records |
| [all-district.json](data/all-district.json) | JSON | All 91 district records |
| [all-ward.json](data/all-ward.json) | JSON | All 1,961 ward records |
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
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
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
| `level` | integer | 1=province, 2=district, 3=ward |
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
divisions/{province-slug}/{district-slug}/
```

Wards are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Zimbabwe Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/zimbabwe-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
