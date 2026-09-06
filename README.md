# My project brief

## The question
Which areas in Lilongwe District, Malawi have poor access to health 
facilities and how does this relate to where people actually live?

## The data I need
- Health facilities – Malawi Ministry of Health via HDX – https://data.humdata.org/dataset/76646ddc-bf8c-43fc-9610-98eaf7edc133 – CSV/Shapefile – ~2 MB
- Road network – OpenStreetMap/HOTOSM via HDX – https://data.humdata.org/group/mwi (search: Malawi roads) – Shapefile/GeoPackage – ~20 MB
- Population distribution – WorldPop via University of Southampton – https://hub.worldpop.org/geodata/summary?id=123 – GeoTIFF – ~20 MB
- Administrative boundaries – National Statistics Office of Malawi via HDX – https://data.humdata.org/dataset/cod-ab-mwi – Shapefile – ~2 MB

## Why it matters
Lilongwe District contains both the densely populated capital city 
and large rural areas where communities may be far from the nearest 
clinic or hospital. Mapping this gap can help the Ministry of Health 
and district planners identify underserved communities and prioritise 
where new facilities or outreach programmes are needed.

## What I will do
Load all four datasets into QGIS and clip them to Lilongwe District 
boundary. Use proximity analysis to calculate distance from populated 
areas to the nearest health facility. Overlay with population density 
to identify where large numbers of people are furthest from a facility.

## What I expect to find
Rural traditional authority areas in the outer parts of Lilongwe 
District are likely to show the greatest access gaps, while the city 
centre and peri-urban areas are comparatively well served.
