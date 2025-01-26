---
layout: page
title: "ATRACKS"
parent: "Tracking algorithms"
order: 12
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

The Algorithm for TRACKing Convective Systems (ATRACKCS, Robledo et al. (2024)) is an open access Python package for the detection and tracking of MCSs. ATRACKCS identifies cold cloud systems using a predefined Tb threshold and converts them into polygons. The algorithm then uses precipitation data to filter out non-precipitating systems. To assign different polygons to the same track in time, ATRACKCS uses a predefined threshold of overlapping area in consecutive times. To deal with the splitting and merging of systems, if multiple systems overlap at the same timestep, ATRACKCS evaluates which systems satisfy the identification criteria and then selects the one with the higher overlapping area to the previous time step to continue the track; the remaining systems are tracked as new ones if satisfy the thresholds. ATRACKCS can be accessed at [https://doi.org/10.5281/zenodo.7025989](https://doi.org/10.5281/zenodo.7025989).



