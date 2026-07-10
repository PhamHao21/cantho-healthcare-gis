```markdown
# Cần Thơ Healthcare GIS Analysis

A hands-on GIS learning project analyzing the spatial distribution,
accessibility, and disease-mapping potential of healthcare
infrastructure in Can Tho City, Vietnam. Built as a portfolio project
to practice core GIS workflows — data acquisition, cartographic
editing, spatial analysis, and geospatial database integration —
using free, open-source tools.

## Overview

The project is organized as three progressive modules, each building
on the previous one's output:

1. **Data Collection & Map Editing** — sourcing and cleaning
   healthcare facility location data, producing a categorized
   thematic map.
2. **Spatial Accessibility Analysis** — buffer and overlay analysis
   to identify underserved areas relative to facility locations.
3. **GIS Database & Epidemiological Mapping** — a geospatial database
   storing simulated case data, joined and rendered as a choropleth
   map.

## Tech Stack

| Category            | Tools                                      |
|----------------------|---------------------------------------------|
| GIS / Cartography    | QGIS                                       |
| Data Source           | OpenStreetMap, Overpass Turbo             |
| Database              | MongoDB Atlas (2dsphere spatial indexing), MongoDB Compass |
| Data Formats           | GeoJSON, CSV                              |

## Repository Structure

```
cantho-healthcare-gis/
├── README.md
├── LICENSE
├── 01-data-collection-mapping/
│   ├── healthcare_facilities_cantho.csv
│   ├── healthcare_facilities_cantho.geojson
│   ├── map_facility_distribution.png
│   └── README.md
├── 02-spatial-accessibility-analysis/
│   ├── ward_boundaries_cantho.geojson
│   ├── coverage_buffer_zones.geojson
│   ├── coverage_gap_areas.geojson
│   ├── map_coverage_gap_analysis.png
│   └── README.md
└── 03-gis-database-epidemiology/
    ├── dengue_cases_raw.csv
    ├── cantho_wards_epidemic.geojson
    ├── map_choropleth_dengue.png
    └── README.md
```

Each module folder contains its own `README.md` with a detailed
workflow description, tool-specific notes, and the resulting map.

## How to Reproduce

1. Install [QGIS](https://qgis.org/) (Long Term Release recommended).
2. Clone this repository:
   ```bash
   git clone https://github.com/PhamHao21/cantho-healthcare-gis-analysis.git
   ```
3. Open the `.geojson` files in each module folder directly in QGIS
   (`Layer → Add Layer → Add Vector Layer`) to inspect or reproduce
   the analysis.
4. For Module 3, case data can optionally be re-imported into a
   MongoDB instance (Atlas or local) with a `2dsphere` index to
   reproduce the join query; the pre-joined output is also provided
   directly as GeoJSON for convenience.

No paid software or API keys are required to reproduce any part of
this project.

## Data Sources & Attribution

- **Healthcare facility locations**: © [OpenStreetMap](https://www.openstreetmap.org/copyright)
  contributors, retrieved via Overpass Turbo, licensed under the Open
  Database License (ODbL). Supplemented manually for major facilities
  missing from OSM coverage.
- **Administrative ward boundaries**: adapted from
  [thanglequoc/vietnamese-provinces-database](https://github.com/thanglequoc/vietnamese-provinces-database),
  licensed under the MIT License.
- **Dengue case data (Module 3)**: simulated for technical
  demonstration purposes only. It does not represent official
  epidemiological records and should not be used for public health
  decision-making.

## Limitations

- Facility coverage depends on OpenStreetMap completeness, which is
  uneven across provincial areas of Vietnam.
- The 3 km accessibility radius used in Module 2 is a simplified,
  uniform assumption; real-world accessibility standards vary between
  urban and rural districts.
- Module 3 uses simulated, not real, health surveillance data.

## Status

This project is a work in progress, built for learning and portfolio
purposes. Data quality, coverage, and analysis depth will be updated
and refined over time.

## License

Code and original data compiled in this repository are released under
the [MIT License](./LICENSE). Third-party data retains its original
license as noted above.

## Author

Phạm Gia Hào — [GitHub](https://github.com/PhamHao21)
```
