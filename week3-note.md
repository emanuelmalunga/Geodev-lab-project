# Week 3 Note — Data Preparation and Quality Checks

## CRS chosen
EPSG:32736 (WGS 84 / UTM Zone 36S) was chosen because it is a metric, 
projected coordinate system appropriate for Malawi, and the project 
question requires distance-based analysis (proximity of population to 
health facilities), which is not reliable in the original geographic 
CRS (EPSG:4326).

## What was reprojected and clipped
Both the hospitals layer and the roads layer, originally downloaded from 
OpenStreetMap via QuickOSM in EPSG:4326, were reprojected to EPSG:32736. 
Both layers were then clipped to the Lilongwe District boundary (sourced 
via QuickOSM, admin_level query) to restrict the data to the study area.

## Quality check results

1. **CRS check** — Both hospitals_analysis_ready and roads_analysis_ready 
   confirmed as EPSG:32736. Pass.
2. **Geometry validity** — Initially found 2 invalid geometries in the 
   hospitals layer and 2 invalid geometries in the roads layer. Fixed 
   using Vector > Geometry Tools > Fix Geometries; re-check confirmed 
   0 invalid geometries remaining in both layers.
3. **Duplicate features** — 0 duplicate geometries found in either the 
   hospitals or roads layer. Pass.
4. **Attribute completeness** — Hospitals: 0 missing `name` values, 0 
   missing facility-type values. Roads: 0 missing `highway` values, 
   1 feature missing a `name` value (expected, as many minor roads/tracks 
   in OSM are unnamed).
5. **Spatial extent** — Initial check showed some hospital points 
   appearing outside the district boundary despite being within Lilongwe. 
   This was traced to a CRS mismatch between the boundary polygon and 
   the point/line layers at the time of clipping. The boundary layer was 
   reprojected to EPSG:32736 and the clip was redone, after which all 
   features correctly fell inside the boundary.

## Problems found and how they were handled
- 2 invalid geometries per layer: fixed directly using Fix Geometries.
- Boundary CRS mismatch causing incorrect clip results: fixed by 
  reprojecting the boundary layer before re-running the clip.
- 1 unnamed road feature: flagged only, not fixed, as this reflects 
  genuine incomplete OSM tagging rather than a processing error.

## Where the analysis-ready files live
- `hospitals_analysis_ready.gpkg`
- `roads_analysis_ready.gpkg`

Both are stored in the root of this repository.
