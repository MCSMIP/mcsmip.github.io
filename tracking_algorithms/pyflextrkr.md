---
layout: page
title: "PyFLEXTRKR"
parent: "Tracking algorithms"
order: 6
---

<style>
  /* Increase font size for this page only */
  body {
    font-size: 21px; /* Adjust this value as needed */
  }

  /* Optionally, target specific elements */
  h1 {
    font-size: 2.5em;
  }

  p {
    font-size: 1.2em;
  }
</style>



The Python FLEXible object TRacKeR ([PyFLEXTRKR](https://github.com/FlexTRKR/PyFLEXTRKR)) is a flexible atmospheric feature tracking software package. The software can track any 2D objects and handle merging and splitting explicitly. PyFLEXTRKR has specific capabilities to track convective clouds from a variety of observations and model simulations. The package uses Dask for scalable parallelization and has been optimized to work on large datasets including global kilometer-scale data. PyFLEXTRKR uses Xarray for I/O and writes netCDF files as tracking outputs.

Currently PyFLEXTRKR supports tracking: 

1. Individual convective cells, 
2. Mesoscale convective systems (MCSs), 
3. General atmospheric objects defined by customizable feature identification functions.

<img src="images/tracker_pyflextrkr_cover_image.gif" alt="Cover Image" style="max-width: 70%; height: auto;">

**Tracking** in PyFLEXTRKR primarily uses object overlap technique, with an option to use advection estimates (2D cross-correlation) to increase overlap probability. Largest overlap objects are tracked continuously, and smaller overlap objects are marked as merging/splitting.

<img src="images/tracker_pyflextrkr_merging_splitting.gif" alt="Cover Image" style="max-width: 70%; height: auto;">

**MCSMIP**: Convective cloud objects were identified using the detect-and-spread approach: 

1. **Label cold cores**: A 10-grid (~100 km) box filter smoothing was first applied to the brightness temperature (T<sub>b</sub>) field, and contiguous areas with the smoothed T<sub>b</sub> < 225 K were labeled as cold cores. 
2. **Spread to cold anvil**: Each cold core was spread outward to surrounding grids until T<sub>b</sub> (original) reached 241 K and grids with the closest distance to nearby cold core were assigned the same label. 

All objects with area > 800 km<sup>2</sup> were tracked based on their area overlap. Objects between two adjacent hours with an area overlap fraction > 0.5 were considered the same track. If more than one object exceeded the overlap fraction, the largest one was tracked continuously, and the smaller ones were labeled as merging or splitting. If a tracked cloud system meets the MCS criteria (MCSMIP-DYAMOND paper, Section 2c), the entire track is labeled as MCS, including the convection initiation period and decay period. Non-MCS cloud objects that merge with or split from an MCS were also included as part of that MCS, and were assigned the same track number in the MCS mask files. 

Example tracking config files for MCSMIP is avaialble under the [/config](https://github.com/FlexTRKR/PyFLEXTRKR/tree/main/config) directory in the Github repository (e.g., [`config_dyamond_summer_obs.yml`](https://github.com/FlexTRKR/PyFLEXTRKR/blob/main/config/config_dyamond_summer_obs.yml)).

Here's the command to run the tracking for MCSMIP:
`python /runscripts/run_mcs_tbpf_saag.py /config/config_dyamond_summer_obs.yml`


---

**Reference**

Feng, Z., Hardin, J., Barnes, H. C., Li, J., Leung, L. R., Varble, A., & Zhang, Z. (2023). PyFLEXTRKR: a flexible feature tracking Python software for convective cloud analysis. Geosci. Model Dev., 16(10), 2753-2776, doi:[10.5194/gmd-16-2753-2023](https://doi.org/10.5194/gmd-16-2753-2023)

