---
layout: page
title: "PyFLEXTRKR"
parent: "trackers"
order: 9
---

## [PyFLEXTRKR](https://github.com/FlexTRKR/PyFLEXTRKR)

---
The Python FLEXible object TRacKeR (PyFLEXTRKR) is a flexible atmospheric feature tracking software package. The software can track any 2D objects and handle merging and splitting explicitly. PyFLEXTRKR has specific capabilities to track convective clouds from a variety of observations and model simulations. The package uses Dask for scalable parallelization and has been optimized to work on large datasets including global kilometer-scale data. PyFLEXTRKR uses Xarray for I/O and writes netCDF files as tracking outputs.

Currently PyFLEXTRKR supports tracking: 

1. Individual convective cells, 
2. Mesoscale convective systems (MCSs), 
3. General atmospheric objects defined by customizable feature identification functions.

<img src="https://portal.nersc.gov/project/m1867/PyFLEXTRKR/figures/cover_image.png" alt="Cover Image" style="max-width: 50%; height: auto;">

**Tracking** in PyFLEXTRKR primarily uses object overlap technique, with an option to use advection estimates (2D cross-correlation) to increase overlap probability. Largest overlap objects are tracked continuously, and smaller overlap objects are marked as merging/splitting.

<img src="https://portal.nersc.gov/project/m1867/PyFLEXTRKR/figures/tracking_merging_splitting.png" alt="Cover Image" style="max-width: 50%; height: auto;">


**Reference**

Feng, Z., Hardin, J., Barnes, H. C., Li, J., Leung, L. R., Varble, A., & Zhang, Z. (2023). PyFLEXTRKR: a flexible feature tracking Python software for convective cloud analysis. Geosci. Model Dev., 16(10), 2753-2776, doi:[10.5194/gmd-16-2753-2023](https://doi.org/10.5194/gmd-16-2753-2023)

