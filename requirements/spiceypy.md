# spiceypy

## Description
- **Main Functionality**: Python wrapper for the SPICE Toolkit, providing access to NASA's planetary data and models.
- **Use in Planetology**: Allows integration of NASA's SPICE data for precise analysis and simulations in planetary missions.

## Technical Requirements
- **Version**: spiceypy 6.0 or higher.

## Links and Resources
- **Official Documentation**: [Spiceypy Documentation](https://spiceypy.readthedocs.io/)

## Code snippet
```python
import spiceypy as spice
import numpy as np

# Load necessary SPICE kernels
spice.furnsh("path/to/spk/kernel.bsp")    # SPK kernel with ephemeris data
spice.furnsh("path/to/pck/kernel.tpc")    # PCK kernel with planetary constants
spice.furnsh("path/to/ls/kernels.tf")     # Leap seconds kernel
spice.furnsh("path/to/fk/kernel.tf")      # Frame kernel

# Define observation time (UTC)
utc_time = "2024-07-11 00:00:00"

# Convert UTC time to ET (Ephemeris Time)
et = spice.str2et(utc_time)

# Define the observer's position on the Moon in planetocentric coordinates (latitude, longitude, radius)
# Example: Near the lunar equator and prime meridian
latitude = 0.0  # degrees
longitude = 0.0  # degrees
radius = 1737.4  # radius of the Moon in km

# Convert observer's planetocentric coordinates to rectangular coordinates
obs_position = spice.latrec(radius, np.radians(longitude), np.radians(latitude))

# Define observer and target
observer = 'MOON'
target = 'SUN'
frame = 'MOON_ME'
abcorr = 'NONE'

# Calculate the position of the Sun relative to the observer on the Moon
sun_position, _ = spice.spkpos(target, et, frame, abcorr, observer)

# Calculate the vector from the observer to the Sun
vector_obs_sun = np.subtract(sun_position, obs_position)

# Convert the observer-to-Sun vector from rectangular to spherical coordinates
range_, lon, lat = spice.reclat(vector_obs_sun)

# Convert latitude to altitude and longitude to azimuth
altitude = np.degrees(lat)
azimuth = np.degrees(lon)

# Ensure azimuth is within the range [0, 360) degrees
azimuth = azimuth % 360

print(f"Altitude: {altitude:.2f} degrees")
print(f"Azimuth: {azimuth:.2f} degrees")

# Unload kernels after use
spice.kclear()

