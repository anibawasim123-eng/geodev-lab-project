# Week 3 – Coordinate Systems and Data Preparation

## Project

**Healthcare Accessibility in Lahore**

### Spatial Question

> Which areas of Lahore are more than 5 km from a mapped healthcare facility?

## Study Area

The study area is Lahore District, Punjab, Pakistan.

The Lahore District boundary was extracted from the Pakistan administrative boundary dataset from DIVA-GIS.

## Coordinate Reference Systems

The original Lahore boundary and healthcare facility layers were in:

**EPSG:4326 – WGS 84**

EPSG:4326 uses geographic coordinates in degrees. Since this project involves distance and area calculations, the layers were reprojected to a projected coordinate reference system:

**EPSG:32643 – WGS 84 / UTM Zone 43N**

This CRS uses metres, making it more appropriate for the 5 km buffer and area calculations used in the analysis.

## Data Preparation

The following preparation steps were completed in QGIS:

1. Checked the CRS of the Lahore District boundary and healthcare facility layers.
2. Reprojected the Lahore District boundary to EPSG:32643.
3. Reprojected the healthcare facility points to EPSG:32643.
4. Created a 5 km buffer around the mapped healthcare facilities.
5. Dissolved the buffer areas into a single coverage area.
6. Clipped the healthcare buffer to the Lahore District boundary.
7. Used a Difference operation to identify areas of Lahore outside the 5 km healthcare coverage area.
8. Created an `area_km2` field to calculate the area of the resulting polygon in square kilometres.
9. Checked the resulting geometry for very small sliver polygons.

## Initial Accessibility Result

The analysis identified approximately:

**892.18 km²**

of Lahore District outside the 5 km straight-line buffer around the mapped healthcare facilities used in this project.

The result was represented by one polygon feature. The geometry was checked for very small sliver polygons, and no additional small features were identified.

## Interpretation

The result indicates that approximately 892.18 km² of the Lahore District is more than 5 km in straight-line distance from the mapped healthcare facilities included in the dataset.

This result refers to the mapped healthcare facilities available in the OpenStreetMap dataset used for this project. It should not be interpreted as representing every healthcare facility in Lahore.

## Limitation

The 5 km accessibility analysis uses straight-line (Euclidean) distance rather than travel distance along roads.

Therefore, the result does not account for the actual road network, road connectivity, travel routes, traffic, or travel time.

A future stage of the project may add a road-network accessibility analysis to compare network-based accessibility with the straight-line result.

## Tools

- QGIS
- QuickOSM
- OpenStreetMap
- DIVA-GIS

## Current Project Status

Week 3 data preparation and initial accessibility analysis completed.

The next stage can investigate road-network accessibility and later present the results through an interactive WebGIS.
