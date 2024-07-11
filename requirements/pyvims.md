# pyVIMS

## Description
- **Main Functionality**: pyvims is a Python library specifically designed for reading and processing data from the Visual and Infrared Mapping Spectrometer (VIMS) on the Cassini spacecraft.
- **Use in Planetology**: Essential for analyzing VIMS data from the Cassini mission, which studied Saturn and its moons. This includes spectral analysis of surface compositions and atmospheres.

## Technical Requirements
- **Dependencies**: Requires numpy, scipy, astropy, and matplotlib.

## Links and Resources
- **Official Documentation**: [PyVims Gtihub repository](https://github.com/seignovert/pyvims)

## code snippet

```python
from pyvims import VIMS
import matplotlib.pyplot as plt

# Load a VIMS data file from the Cassini mission
vims_data = VIMS('path/to/vims_data.cub')

# Access spectral data and metadata
spectral_cube = vims_data.cube
wavelengths = vims_data.wavelengths

# Example: Plot the spectrum of a specific pixel
pixel_spectrum = spectral_cube[:, 100, 100]  # Pixel at (100, 100)
plt.plot(wavelengths, pixel_spectrum)
plt.xlabel('Wavelength (µm)')
plt.ylabel('Reflectance')
plt.title('Spectrum of Pixel (100, 100)')
plt.show()

# Perform further analysis, such as identifying surface compositions
# Example: Calculate average spectrum of the entire dataset
average_spectrum = spectral_cube.mean(axis=(1, 2))
plt.plot(wavelengths, average_spectrum)
plt.xlabel('Wavelength (µm)')
plt.ylabel('Average Reflectance')
plt.title('Average Spectrum of VIMS Data')
plt.show()
