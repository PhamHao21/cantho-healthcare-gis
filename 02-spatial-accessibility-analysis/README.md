# 2. Spatial Accessibility Analysis

## Objective
Identify areas of Can Tho City that fall outside a reasonable travel
distance from any healthcare facility, to support planning-oriented
spatial analysis.

## Workflow
1. Loaded ward-level administrative boundaries for Can Tho City.
2. Generated a 3 km buffer zone around each healthcare facility point
   (from Module 1) using QGIS's Buffer tool.
3. Merged overlapping buffers into a single coverage area (Dissolve).
4. Computed the spatial difference between the full city boundary and
   the coverage area (Difference) to isolate underserved zones —
   referred to here as "healthcare coverage gaps."
5. Rendered the result as a map layering coverage gaps, buffer zones,
   and facility points.

## Method Notes
A single 3 km radius was used city-wide as a simplified accessibility
threshold. In practice, accessibility standards vary between dense
urban districts (e.g. Ninh Kieu) and rural areas (e.g. Co Do, Phong
Dien), which is a limitation acknowledged here for future refinement.

## Tools
QGIS (Buffer, Dissolve, Difference geoprocessing tools)

## Files
- `ward_boundaries_cantho.geojson` — administrative ward boundaries
  (see root README for data source attribution)
- `coverage_buffer_zones.geojson` — dissolved 3 km buffer coverage
- `coverage_gap_areas.geojson` — resulting underserved areas
- `map_coverage_gap_analysis.png` — final exported map

![Coverage gap analysis map](./map_coverage_gap_analysis.png)
