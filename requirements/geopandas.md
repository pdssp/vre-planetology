# geopandas

## Description
- **Main Functionality**: GeoPandas extends Pandas to provide support for geometric operations on geospatial data
- **Use in Planetology**: Useful for handling and analyzing vector data from planetary surfaces

## Technical Requirements
- **Dependencies**: Requires pandas, shapely, fiona, pyproj, and gdal.

## Links and Resources
- **Official Documentation**: [Pandas Documentation](https://geopandas.org/)
- **Additional References**: [GeoPandas Tutorials](https://www.datacamp.com/tutorial/geopandas-tutorial-geospatial-analysis)

## code snippet

```python
import geopandas as gpd

# Load a shapefile containing geological features of Mars
gdf = gpd.read_file('mars_geological_features.shp')

# Display the first few rows of the GeoDataFrame
print(gdf.head())

# Plot the geological features
gdf.plot()
