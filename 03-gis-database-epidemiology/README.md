# 3. GIS Database & Epidemiological Mapping

## Objective
Build a geospatial database to store and visualize disease case data
by administrative ward, demonstrating a full GIS + database workflow
from raw data to cartographic output.

## Workflow
1. Prepared simulated dengue fever case counts per ward (see note
   below on data authenticity).
2. Loaded ward boundary geometries and case data into MongoDB Atlas,
   using a `2dsphere` index for spatial queries.
3. Queried and joined case data with ward geometries via MongoDB
   Compass.
4. Exported the joined result back to GeoJSON and rendered it in
   QGIS as a graduated (choropleth) map by case count.

## ⚠️ Data Disclaimer
Case count data in this module is **simulated for technical
demonstration purposes only**. It does not represent real
epidemiological records and should not be interpreted as official
public health data.

## Tools
MongoDB Atlas · MongoDB Compass · QGIS (Graduated Symbology)

## Files
- `dengue_cases_raw.csv` — simulated raw case data (input to MongoDB)
- `cantho_wards_epidemic.geojson` — joined output (boundaries + case
  counts), exported from Atlas for QGIS rendering
- `map_choropleth_dengue.png` — final exported choropleth map

![Dengue choropleth map](./map_choropleth_dengue.png)
