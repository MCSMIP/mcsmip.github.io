---
layout: page
title: "tobac"
parent: "Tracking algorithms"
order: 9
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


*tobac* (Tracking and Object-based Analysis of Clodus) is a scientific Python package for detecting, tracking, and analyzing clouds and other atmospheric phenomena. tobac is unique in its ability to track phenomena using **any variable** on **any grid**, including radar data, satellite observations, and numerical model output. Due to its modular and flexible design, tobac is a general toolset that can be used for tracking all kinds of atmosheric phenomena related to storm formation, from small scales (e.g. updrafts) to large scales (e.g. atmospheric rivers).


The main elements of *tobac* are:

1. **Data input and output** - Xarray and pandas 
2. **Data filtering** - Gaussian smoothing and wave-length based filtering
3. **Feature detection** - works in 3D and with multiple thresholds
4. **Segmentation of cloud areas and volumes** - works in 3D and across different data sets (e.g. get the precipitation volume associated with detected clouds) 
5. **Trajectory linking** - uses propagation speed and works across periodic boundaries 
6. **Object-based analysis and visualization** - includes the identification of mergers and splitters in the track database


*tobac* developed with an open, multi-institutional international community, and has been built from the ground up in support of open science. Detailed documentation can be found [here](https://tobac.readthedocs.io/en/latest/). Any user feedback is welcome and users are invited to leave commentsand questions in the [GitHub discussion forum of *tobac*](https://github.com/tobac-project/tobac/discussions) or, if it concerns bug reports or specific user requests, a [GitHub issue](https://github.com/tobac-project/tobac/issues). Release announcements, workshop and conference announcements, and other information of interest to the broader *tobac* users group are sent to the [tobac core group](https://groups.google.com/g/tobac/about) mailing list. If you are interested in contributing to the development of tobac, users are invited to join the [tobac developers](https://groups.google.com/u/0/g/tobac-developers) mailing list. 


**References**

Heikenfeld, M., Marinescu, P. J., Christensen, M., Watson-Parris, D., Senf, F., van den Heever, S. C., and Stier, P.: tobac 1.2: towards a flexible framework for tracking and analysis of clouds in diverse datasets, Geosci. Model Dev., 12, 4551–4570, [https://doi.org/10.5194/gmd-12-4551-2019](https://doi.org/10.5194/gmd-12-4551-2019), 2019.

