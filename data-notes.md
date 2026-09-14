# Data Notes — Lahore Healthcare Accessibility

## Project

**Project:** Healthcare Accessibility in Lahore

**Spatial Question:**  
Which areas of Lahore are more than 5 km from a mapped healthcare facility?

---

## Dataset 1 — Lahore District Boundary

**Dataset:** Lahore District administrative boundary

**Original source:** DIVA-GIS

**Source link:** https://www.diva-gis.org/gdata

**Original data:** Pakistan administrative boundaries

**Processing:** The Lahore District feature was extracted from the Pakistan administrative boundary dataset.

**Current file:** `lahore_boundary.gpkg`

**Geometry:** Polygon

**Use in project:** Defines the study area for the spatial analysis.

---

## Dataset 2 — Healthcare Facilities

**Dataset:** Hospitals / healthcare facilities in Lahore

**Source:** OpenStreetMap contributors

**Source link:** https://www.openstreetmap.org/

**Collection method:** Data was obtained using the QuickOSM plugin in QGIS.

**Current file:** `Lahore_hospital_data`

**Number of features:** 185

**Geometry:** Point

**OSM geometry type:** Node

**Important attributes:**
- `name` — facility/hospital name
- `amenity` — healthcare-related OSM tag
- `healthcare` — healthcare classification where available
- `emergency` — emergency service information where available
- `addr:street` — street address where available
- `addr:city` — city information where available

**Data quality observation:** Many attribute fields contain NULL values. This means some facilities have incomplete attribute information.

**Use in project:** Provides the locations of mapped healthcare facilities used for the 5 km accessibility analysis.

**License:** OpenStreetMap data is available under the Open Database License (ODbL).

**License link:** https://www.openstreetmap.org/copyright
