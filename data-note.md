# Data Note

## Health Facilities (Hospitals)
- Source: OpenStreetMap, via QuickOSM (Key: amenity, Value: hospital, Area: Lilongwe)
- Feature count: 5
- Geometry type: Point
- Key columns: name, osm_id, amenity, phone, operator, operator_type, street, 
  city, postcode, opening_hours, website, healthcare
- Gaps/missing values: Only 2 of 5 records have a phone number, and only 1 
  record (DNA Hub Africa) has a complete address, postcode, opening hours, 
  and website. Operator information is recorded for only 1 facility 
  (Kalumbu Hospital, listed as government-operated). None of the records 
  have payment-method (debit/credit card) information filled in.

## Roads
- Source: OpenStreetMap, via QuickOSM (Key: highway, no value, Area: Lilongwe)
- Feature count: 45,487
- Geometry type: LineString
- Key columns: full_id, osm_id, osm_type, highway, plus over a dozen optional 
  tag columns (e.g. wheelchair, lit, kerb, bin, bench, advertising, waterway)
- Gaps/missing values: Of the 20+ columns present, only `highway` and the 
  ID fields (full_id, osm_id, osm_type) are consistently populated across 
  the dataset. The remaining columns are optional OSM tags that apply to 
  only a small number of specific features, so they are blank for the 
  vast majority of the 45,487 road segments.
