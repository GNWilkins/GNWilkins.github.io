# GES 486 Project 1 (By Gabriel Wilkins)
The front-end of this project can be found [here](../project1_486/West_Virginia_Health.md)

## Topic
Poverty rate and other societal indicators in West Virginia spatially related to former and current mining or other industrial sites.

## Data
Data was gathered from [the West Virginia GIS Technical Center](http://wvgis.wvu.edu/data/data.php).
Both raster and vector data were gathered, with data including: land use and land cover, census tracts, industrial buildings/sites/parks, mineral operations and abandoned mines, and roads/railroads.

## Transformations and Subsets
Some data files were merged together, such as rivers and lakes, different railroad files, and industrial and mine sites.
Other data were transformed, predominantly the land use and land cover raster so to merge some similar data values together.

## Analysis
Analysis will include buffers around industrial sites and land uses such as mining, as well as the intersections of such buffers with census tract polygons. The next step will involve comparing the area of intersection with demographic, economic, and social characteristics of census tracts.

## Outputs
### Expected outputs include:
- Vector shapefile created from the land use/land cover raster
- Buffers of certain land use polygons (created by vectorization) and industrial/mining shapefile polygons
- Intersection of these buffers with individuals census tracts.
- Categorized shapefile showing output of comparison of buffer intersection/overlap with tract demographic, economic, and social characteristics.
