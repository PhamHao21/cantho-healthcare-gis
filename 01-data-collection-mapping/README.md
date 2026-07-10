# 1. Data Collection & Map Editing

## Objective
Collect and map the geographic distribution of healthcare facilities
(hospitals, clinics, health centers) across Can Tho City to build a
categorized thematic base map.

## Workflow
1. Queried OpenStreetMap via Overpass Turbo for nodes/ways tagged
   `amenity=hospital|clinic|doctors|pharmacy` and `healthcare=*`
   within Can Tho City boundaries.
2. Supplemented missing major facilities manually (coordinates
   verified via Google Maps), since OSM coverage in provincial areas
   is often incomplete.
3. Cleaned and standardized facility names and categories.
4. Edited the final map in QGIS: categorized symbology by facility
   type, added legend, scale bar, north arrow, and title.

## Data Fields

| Field       | Description                                            |
|-------------|----------------------------------------------------------|
| `ten`       | Facility name                                            |
| `lat`,`long`| Coordinates (WGS84)                                       |
| `loai_hinh` | Facility type (Hospital / Clinic / Health Authority)       |

## Tools
QGIS · Overpass Turbo · OpenStreetMap

## Files
- `healthcare_facilities_cantho.csv` — raw collected data
- `healthcare_facilities_cantho.geojson` — cleaned, GIS-ready dataset
- `map_facility_distribution.png` — final exported map

## Data Sources
Facility locations © OpenStreetMap contributors, available under the
[Open Database License](https://www.openstreetmap.org/copyright).

![Facility distribution map](./map_facility_distribution.png)
