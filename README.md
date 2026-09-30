GeoDev Lab Africa — Health Facility Access, Lilongwe District, Malawi
My question

Which areas in Lilongwe District, Malawi have poor access to health facilities, and how does that relate to where people live?

Answer

Health facilities in Lilongwe District are heavily concentrated in the city centre, where dozens of facilities and their 5 km buffers overlap. Outlying Traditional Authorities are thinly served: TA Masula, for example, has only three health facilities, and their buffers overlap each other rather than spreading out to cover the TA. Straight-line distance also overstates real access, since it ignores roads and population. See month-1-summary.md and buffer map.png for the full result.

Project by week
Week 1 — Project brief: project-brief.md The question, and a source link, format and size for every dataset.
Week 2 — Data notes: data-note.md What was downloaded from OpenStreetMap via QuickOSM: feature counts, key columns, geometry type, and gaps/missing values. Raw data: hospitals_lilongwe.gpkg, highways_lilongwe.gpkg
Week 3 — Data preparation and quality checks: week3-note.md Reprojection to EPSG:32736, clipping to Lilongwe District, and the five quality checks (CRS, geometry validity, duplicates, attribute completeness, spatial extent), including a boundary CRS mismatch that was found and fixed. Analysis-ready files: hospitals_lilongwe_utm.gpkg, road_utm.gpkg
Week 4 — Analysis: month-1-summary.md A 5 km buffer around each of the 197 health facilities, checked four ways (map, row count, one feature measured by hand, empty geometry). Map: buffer map.png

Built over twelve months with GeoDev Lab Africa, Cohort One.
