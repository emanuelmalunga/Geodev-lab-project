# Month 1 Summary

## My question
Which areas in Lilongwe District, Malawi have poor access to health facilities, and how does that relate to where people live?

## The operation I ran and why
I ran a 5 km buffer around each of the 197 health facilities in `hospitals_lilongwe_utm`, in EPSG:32736 (WGS 84 / UTM zone 36S), so the buffer distance is in meters. A buffer fits the first part of my question: the areas outside the circles are the places farthest from a facility. I left "Dissolve result" unticked so each facility kept its own circle and the row count could be checked (197 in, 197 out).

The 197 facilities are: clinic (84), dispensary (48), health centre (43), hospital (10), health post (10), district hospital (1) and central hospital (1).

The result is mapped in `buffer_map.png`. The basemap is OpenStreetMap tiles (© OpenStreetMap contributors), and the boundaries drawn are the Traditional Authority (TA) boundaries.

## What I expected and what I got

**Expected:** I expected the buffer to return 197 features, one 5 km circle for each health facility in `hospitals_lilongwe_utm`, each just under 78 km² (π × 5²). With 197 facilities in one district, I expected many circles to overlap heavily, so I would not sum the areas. I expected the circles to cover most of the area around the city and leave gaps in remote outer parts of the district. I expected no empty geometries, because the points were checked and fixed in Week 3.

**Got:**
- Feature count: 197 buffers for 197 facilities, as expected.
- Overlap and coverage: circles overlap heavily in the city centre and leave gaps in the outer TAs, as expected. For example, TA Masula has only three facilities, their circles overlap, and they do not cover the whole TA.
- Circle size: I checked the radius (see check 3) but did not measure circle areas.


## Checked four ways
1. **Map:** the circles sit on their facilities. They pile up in the city centre, several run past the district boundary, and the outer TAs have visible gaps. 
2. **Row count:** expected 197, found 197. At first I read 59, but that came from a filter left switched on in the attribute table, not from the buffer output. After choosing "Show All Features" the table showed 197.
3. **Verified one feature by hand:** using the Measure Line tool from the Bwese facility to the edge of its own buffer, I measured 4,922 m against an expected 5,000 m (about 1.6% short). This is consistent with QGIS drawing the circle as straight-edged segments, where the edge sits slightly inside the true radius except at the vertices.


## Problems found
- **Attribute table filter:** the filter that showed 59 rows made my first row count and empty-geometry check look wrong. I removed it and re-ran both checks on all 197 rows.


## What surprised me
The facilities are heavily concentrated in the city centre, where the circles overlap so much that it is hard to see individual facilities. Outside the centre, coverage is thin: TA Masula has only three facilities, and even those overlap each other, leaving much of the TA outside any 5 km circle. A 5 km circle is also a rough measure, because it ignores roads, terrain and how many people live inside it.

## What data I still need
- **Population data** (for example WorldPop), to count how many people live outside the circles, since distance alone does not show who is affected.
- **Travel distance or time along roads**, because a straight-line circle ignores the real route to a facility.
- **A check that the facility list is complete and up to date** for the outer TAs, so gaps on the map reflect real gaps and not missing records.
- **Facility capacity or service level**, since a clinic and a central hospital count the same in a simple buffer.
