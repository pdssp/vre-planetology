# PyQGIS plugin for Jupyter

## Description
- **Main Functionality**: PyQGIS is the Python library for QGIS, a powerful open-source geographic information system. It allows for scripting and automation of geospatial data analysis and visualization within QGIS.
- **Use in Planetology**: Enables advanced geospatial analysis and visualization of planetary data, such as mapping rover paths, analyzing surface features, and processing satellite imagery of other planets.
 
## Technical Requirements
- **Dependencies**: Requires qgis and python3-qgis packages.

## Links and Resources
- **Official Documentation**: [PyQGIS Documentation](https://docs.qgis.org/3.34/en/docs/pyqgis_developer_cookbook/index.html)
- **Additional References**: [PyQGIS with Jupyter](https://anitagraser.com/2023/01/21/pyqgis-jupyter-notebooks-on-windows-using-conda/)

## code snippet

```python
import sys
import os

import qgis
from qgis.gui import *
from qgis.core import *
from qgis.utils import plugins
from PyQt5.QtCore import *
from qgis.analysis import QgsNativeAlgorithms

sys.path.append('/usr/share/qgis/python/plugins/')
sys.path.append('/usr/share/qgis/python/')

QgsApplication.setPrefixPath('/usr', True)
app = QgsApplication([], False)
app.initQgis()

import processing
from processing.core.Processing import Processing
Processing.initialize()

QgsApplication.processingRegistry().addProvider(QgsNativeAlgorithms())
for alg in QgsApplication.processingRegistry().algorithms():
        print(alg.id(), "--->", alg.displayName())

# Stop QGIS appllication
app.exitQgis()
app.exit()
