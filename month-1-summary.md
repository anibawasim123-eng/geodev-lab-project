# Month 1 Summary – Healthcare Accessibility in Lahore

## Question

Which areas of Lahore are more than 5 km from a mapped healthcare facility?

## Spatial Operation

The main spatial operation was a **5 km buffer** around mapped healthcare facilities.

The healthcare facilities were represented as point features and the analysis was carried out in the projected CRS **EPSG:32643 – WGS 84 / UTM zone 43N**.

The buffer was used because the project question asks which areas are more than 5 km from healthcare facilities. Creating a 5 km buffer around each mapped facility provides a spatial representation of areas within 5 km of those facilities. I then used this coverage area to identify areas outside the 5 km coverage.

## What I Expected

There were **185 mapped healthcare features** in the healthcare dataset.

I expected the 5 km buffers to overlap in many locations because healthcare facilities are distributed across the study area. After dissolving the buffers, I expected the result to form coverage areas rather than 185 separate buffer polygons.

I also expected some parts of Lahore to remain outside the 5 km coverage.

## What I Got

The Lahore District area was approximately:

**1,843.67 km²**

The area outside the 5 km healthcare coverage was:

**892.18 km²**

This represents approximately:

**48.39% of Lahore District**

The area within the 5 km coverage was approximately:

**951.49 km²**

This represents approximately:

**51.61% of Lahore District**

The final area outside the buffer was a **MultiPolygon**, meaning that the areas outside the 5 km coverage can consist of several separate areas.

## Four Checks

### 1. Map Check

I inspected the healthcare points, Lahore boundary and 5 km buffer together in QGIS. The buffer surrounded the mapped healthcare facilities and the clipped result remained within the Lahore study area.

### 2. Row Count Check

The input healthcare layer contained **185 features**.

Because the buffers were dissolved, I did not expect the output to contain 185 separate polygons. The dissolved result represents the combined coverage area of the mapped healthcare facilities.

### 3. Manual Feature Check

I selected an individual mapped healthcare facility and inspected it against the 5 km buffer in QGIS. The healthcare point was located inside the buffer.

### 4. Empty Geometry Check

I inspected the resulting analysis layer for empty or missing geometries. No empty geometry problem was identified.

## What Surprised Me

The result showed that approximately **48.39% of Lahore District** was outside the 5 km straight-line coverage area of the mapped healthcare facilities used in this analysis.

The result was also a MultiPolygon, showing that the areas outside the coverage were separated into multiple areas rather than forming one continuous region.

## What Data I Still Need

The current analysis uses mapped healthcare facilities from OpenStreetMap. Some healthcare facilities may not be represented in the dataset.

The analysis also uses straight-line distance rather than travel distance along roads.

For a future extension, I would like to obtain and analyse the OpenStreetMap road network and compare straight-line accessibility with road-network accessibility.

## Limitations

The result should not be interpreted as meaning that 48.39% of Lahore has no healthcare access.

It represents areas more than 5 km from the mapped healthcare facilities included in this dataset.

Actual accessibility can also depend on road networks, travel time, transport availability, facility capacity and the type of healthcare service available.

## Data and Tools

- QGIS
- QuickOSM
- OpenStreetMap healthcare facilities
- DIVA-GIS Lahore District boundary
- Projected CRS: EPSG:32643

## Month 1 Status

The Month 1 project established a spatial question, collected and prepared spatial data, transformed the data into a projected CRS, and performed a spatial accessibility analysis using a 5 km buffer.

A future extension will investigate healthcare accessibility using the road network.
