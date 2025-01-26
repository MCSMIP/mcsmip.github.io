---
layout: page
title: "TIMPS"
parent: "Tracking algorithms"
order: 11
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


etects intense core areas and spreads to surrounding weak regions. The “cascading thresholds” use multiple thresholds (high-intensity area, moderate-intensity area, and low-intensity area), where higher intensity area spreads into lower intensity region, and cascading continues until it reaches the outer boundary. Past studies show that convection depth (minimum Tb) varies with region; hence, different thresholds are required in various regions to identify intense convection areas. Therefore, TIMPS uses variable thresholds (normalized thresholds) that depend on the system’s minimum Tb to identify high and moderate-intensity areas. Following Feng et al. (2021), we use Tb < 241 K as the low-intensity threshold for the outer boundary. For each contiguous IR area defined by the outer boundary, minimum Tb is determined; then the system-dependent high-intensity threshold is calculated as 241 – 0.50 * (241 – minimum Tb) and the moderate intensity threshold as 241 – 0.25 * (241 – minimum Tb). Then, spatial objects are identified in each contiguous area through cascading method from higher to lower intensity areas.

After spatial segmentation, the FiT program uses the overlapping method to link between time steps. For each object (spatial segment) in the current time step, the system in the previous timestep with maximum overlap will be linked. If multiple objects at the current time are linked to the same system in the previous time step, a split event is assumed, and objects are treated as pieces from the same system.  A sample configuration file (namelist_TIMPS_IR.py) can be accessed on Zenodo (Rajagopal 2025).