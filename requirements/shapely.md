# Shapely

## Description
- **Main Functionality**: Python library for geometric operations using geometric objects.
- **Use in Planetology**: Enables geometric calculations and spatial analysis in planetary science.

## Technical Requirements
- **Version**: Shapely 2.0 or higher.

## Links and Resources
- **Official Documentation**: [Shapely Documentation](https://shapely.readthedocs.io/en/stable/)

## Code snippet

```python
from shapely.geometry import Point, Polygon

# Create a point representing a rover landing site on Mars
landing_site = Point(6.0, 135.0)

# Create a polygon representing an exploration area
exploration_area = Polygon([(5.0, 135.0), (5.5, 135.0), (5.5, 135.5), (5.0, 135.5)])

# Check if the landing site is within the exploration area
is_within = landing_site.within(exploration_area)

print(f"Landing site within exploration area: {is_within}")
