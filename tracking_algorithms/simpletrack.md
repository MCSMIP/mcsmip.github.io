---
layout: page
title: "simpleTrack"
parent: "Tracking algorithms"
order: 13 
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


Originally developed for tracking convective cells from radar observations [(Stein et al., 2015)](https://doi.org/10.1175/BAMS-D-13-00279.1), simpleTrack (also called DYMECS in the literature) is a versatile storm-tracking algorithm, with further documented applications to phenomena including MCSs and heavy rainfall events (Crook et al., 2019; Müller et al., 2023; Crook et al., 2024). The algorithm uses a single 2D field and tracks clusters which meet prescribed cut-off and area thresholds: in this case, clusters of more than 9 pixels (~1000 km2) with Tb < 241K. To join temporally disparate clusters into storm tracks, a velocity field calculated from cross-correlation of two contiguous timesteps is used to advect the earlier timestep forwards to the later time. Clusters where the fractional overlap in the later timestep between the advected and “true” cluster is greater than 0.6 are then considered part of the same storm. Identification of storm initiations and mergers then proceeds logically: new storms are considered to initiate if no overlap is found with an advected cluster, while multiple advected clusters overlapping a single cluster in the later timestep are considered a merger. To limit storm tracks to MCSs for the purposes of this study, tracks were first filtered based on the prescribed lifetime Tb characteristics. Rainfall masks were then generated retrospectively for every Tb cluster within a candidate MCS track, and the set of tracks again filtered to finally meet the common criteria. The specific implementation of the algorithm used for this study is thus relatively computationally inefficient. The python code underlying the general simpleTrack algorithm is openly available from [Github](https://github.com/thmstein/simple-track).