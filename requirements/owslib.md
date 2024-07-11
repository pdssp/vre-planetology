# OWSlib

## Description
- **Main Functionality**: OWSLib is a Python package for client programming with OGC (Open Geospatial Consortium) web services.
- **Use in Planetology**: Enables access to planetary data through OGC-compliant web services, such as WMS, WFS, and WCS.

## Technical Requirements
- **Dependencies**: Requires requests, python-dateutil, and other specific dependencies depending on the OGC service being accessed.
  
## Links and Resources
- **Official Documentation**: [OWSlib Documentation](https://owslib.readthedocs.io/)
- **Additional References**: [GeoPython Tutorials](https://github.com/geopython/geopython-workshop/tree/master/workshop)

## code snippet

```python
from owslib.wms import WebMapService

# Connect to a WMS service providing Mars surface imagery
wms = WebMapService('http://your-wms-url', version='1.3.0')

# List available layers
layers = list(wms.contents)
print(layers)

# Get a map image
img = wms.getmap(layers=['layer_name'],
                 srs='EPSG:4326',
                 bbox=(minx, miny, maxx, maxy),
                 size=(300, 300),
                 format='image/jpeg')

# Save the map image
with open('mars_map.jpg', 'wb') as f:
    f.write(img.read())

