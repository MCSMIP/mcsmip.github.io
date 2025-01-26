---
layout: page
title: "KFyAO"
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


The Kalman Filter and Area Overlapping (KFyAO) is a freely available package written in Matlab for 2D feature tracking. This algorithm builds on the methods developed by Huang et al. (2018), which are based solely on Tb and have been widely used in our previous studies utilizing both satellite observations and model simulations (Dong et al., 2020; Dong et al., 2021). To comply with the MCSMIP protocol, we modified the package to include surface precipitation as an additional constraint for MCS detection and tracking. The updated algorithm involves two steps: First, MCS candidates are identified based on a Tb threshold and a minimum area coverage threshold, set to 241 K and 40,000 km², respectively, in this study. Candidates without an embedded cold core with Tb less than 225 K are excluded. After initial identification, a tracking procedure is performed to link those identified objects. Candidates in consecutive timeframes with more than 15% overlapping area are classified as the same MCS. For small or fast-moving MCSs with insufficient overlapping between timeframes, a Kalman filter approach estimates the movement of potential MCSs. The tracked MCSs are further screened by the following criteria: (1) Duration of at least 4 continuous hours; (2) Minimum peak precipitation of 10 mm h–1 at least one pixel within the MCS for 4 continuous hours, regardless of the MCS track duration. (3) Minimum rainfall volume of 20,000 km² mm h–1 at least once during the MCS lifetime.