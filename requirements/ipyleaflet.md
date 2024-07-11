# ipyleaflet

## Description
- **Main Functionality**: ipyleaflet is a Python library that provides interactive maps for the Jupyter notebook, built on top of leaflet.js.
- **Use in Planetology**: Useful for visualizing planetary data on interactive maps, such as plotting rover paths, landing sites, or observational data on maps of other planets.
 
## Technical Requirements
- **Dependencies**: Requires ipywidgets, traitlets, and numpy.

## Links and Resources
- **Official Documentation**: [ipyleaflet Documentation](https://ipyleaflet.readthedocs.io/)
- **Additional References**: [ipyleaflet Github repository](https://github.com/jupyter-widgets/ipyleaflet)

## code snippet

```python
from ipyleaflet import Map, WMSLayer, LayersControl

wmsLayer = WMSLayer(
    url='https://planetarymaps.usgs.gov/cgi-bin/mapserv?map=/maps/mars/mars_simp_cyl.map',
    layers='MOLA_THEMIS_blend',
    name='MOLA THEMIS Blend (MDIM2.1)',
    crs=dict(name="EPSG4326", custom=False)
)

mars_map = Map(
    layers=(wmsLayer, ), 
    center=(4.5, 137.4),  # Gale Crater on Mars
    crs=dict(name="EPSG4326", custom=False)
)
landing_site_marker = Marker(location=(4.5, 137.4), draggable=False)
mars_map.add_layer(landing_site_marker)
mars_map.add_control(LayersControl())
mars_map
