# RasterIO

## Description
- **Main Functionality**: Rasterio is a Python library for reading and writing raster datasets.
- **Use in Planetology**: Essential for processing planetary raster data, such as analyzing satellite images or digital elevation models of other planets.

## Technical Requirements
- **Dependencies**: Requires GDAL
  
## Links and Resources
- **Official Documentation**: [RasterIO Documentation](https://rasterio.readthedocs.io/)
- **Additional References**: [Rasterio GitHub Repository](https://github.com/mapbox/rasterio)

## code snippet

```python
import rasterio

# Open a Mars surface image file
dataset = rasterio.open('path/to/mars_image.tif')

# Read raster data
data = dataset.read(1)

print(f"Image shape: {data.shape}")
print(f"Image data: {data}")

