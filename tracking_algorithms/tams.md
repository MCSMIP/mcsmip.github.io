---
layout: page
title: "TAMS"
parent: "Tracking algorithms"
order: 10
---

<img src="https://raw.githubusercontent.com/knubez/TAMS/main/docs/_static/TAMS-logo.png"
 alt="TAMS logo"
 width="200">

**TAMS** (**T**racking **A**lgorithm for **M**esoscale Convective **S**ystems) is an MCS tracker and classifier. TAMS was [originally developed](https://doi.org/10.1175/MWR-D-19-0070.1) for tracking and analyzing MCSs associated with African easterly waves (AEWs). The currently developed TAMS is a scientific Python package. **TAMS** uses the [GeoPandas dataframe](https://geopandas.org/en/stable/docs/reference/api/geopandas.GeoDataFrame.html) data structure to store polygon shapes of the elements to be tracked. It is a grid-independent MCS identifier and tracker, and as such, it can be applied for both simulated and observed MCSs. It is available to be installed via `pip` or `conda`/`mamba`.

```
pip install tams
```

```
conda install -c conda-forge tams
```

**TAMS** has four main steps: 

1. **Identify** – Through xarray and Shapely/GeoPandas, cloud elements (CEs) that are MCS candidates via default criteria are identified through temperature thresholds (if using satellite data) or cloud top temperature proxy (model data) 
2. **Tracking** – Overlap method and optional cloud projection in the *x* direction
3. **Classification** – Based on default criteria considering shape, size, and duration, each MCS is classified into one of four possible categories 
4. **Assignment of rainfall (or variable of choice)** – Through the use of the helper function `tams.data_in_contours`, a variable of choice can be added to each CE in order to study the MCS evolution across different statistical analysis and atmospheric variables 

Currently, **Identify**, **Assignment**, and some post-processing can be done in parallel.

### Settings

Users can choose outer and core thresholds of CEs for object detection, optionally define zonal projection velocity, and choose the % overlap threshold for time matching.

### Helper functions and utilities

Users can use the eccentricity calculation function as a measure of the MCS shape. Other functions include plotting MCS tracks, loading sample [MSG](https://www.eumetsat.int/0-degree-service) ch9 satellite data, and [MPAS](https://mpas-dev.github.io/) data. Jupyter Notebooks and examples are available for calculating brightness temperature from EUMETSAT, MPAS Cloud Top Temperature from OLR, and others.

The documentation is available at <https://tams.readthedocs.io>.

---

### References

Kelly M. Núñez Ocasio, Jenni L. Evans, and George S. Young. Tracking Mesoscale Convective Systems that are Potential Candidates for Tropical Cyclogenesis. *Monthly Weather Review*, 148(2):655 – 669, Feb 2020. [doi:10.1175/MWR-D-19-0070.1](https://doi.org/10.1175/MWR-D-19-0070.1).

Kelly M. Núñez Ocasio, Jenni L. Evans, and George S. Young. A Wave-Relative Framework Analysis of AEW–MCS Interactions Leading to Tropical Cyclogenesis. *Monthly Weather Review*, 148(11):4657 – 4671, Nov 2020. [doi:10.1175/MWR-D-20-0152.1](https://doi.org/10.1175/MWR-D-20-0152.1).

Kelly M. Núñez Ocasio and Zachary L. Moon. TAMS: a tracking, classifying, and variable-assigning algorithm for mesoscale convective systems in simulated and satellite-derived datasets. *Geoscientific Model Development*, 17(15):6035–6049, Aug 2024. [doi:10.5194/gmd-17-6035-2024](https://doi.org/10.5194/gmd-17-6035-2024).
