# gdal

## Description
- **Main Functionality**: GDAL (Geospatial Data Abstraction Library) is a library for reading and writing raster and vector geospatial data formats
- **Use in Planetology**: Essential for processing planetary raster datasets, such as surface elevation models or spectral data.

## Technical Requirements
- **Dependencies**: None

## Links and Resources
- **Official Documentation**: [Gdal Documentation](https://gdal.org)
- **Additional References**: [Gdal Tutorials](https://pcjericks.github.io/py-gdalogr-cookbook/)

## code snippet

```python
from osgeo import gdal

# Open a Mars surface elevation model file
dataset = gdal.Open('path/to/mars_elevation_model.tif')

# Read raster data
band = dataset.GetRasterBand(1)
elevation_data = band.ReadAsArray()

print(f"Elevation data: {elevation_data}")
