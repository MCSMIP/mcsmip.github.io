---
layout: page
title: "Experimental design"
order: 1
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


## Intercomparison of tracking algorithms

Existing storm tracking algorithms are based on different methodologies and therefore have different capabilities for tracking MCSs. Some trackers are specifically designed for MCS tracking, while others are general feature trackers that require post-processing. In this intercomparison project, we run ten different trackers with their preferred configuration to track convective clouds using infrared brightness temperatures (Tb) and surface precipitation. We identify MCSs using consistent criteria to highlight the differences between tracking methods that are independent on threshold choices and tracking criteria.


## Tracking criteria

Mesoscale convective systems (MCSs) are defined using both a cloud shield identified in infrared brightness temperatures (Tb) and surface precipitation:

- Cloud shield area with Tb < 241 K must be at least 40,000 km<sup>2</sup> and persists for at least 4 continuous hours, and must contain Tb < 225 K at least once during those hours.
- Must contain minimum peak precipitation of 10 mm h<sup>-1</sup> inside the cloud shield for 4 continuous hours.
- Must reach a minimum rainfall volume of 20,000 km<sup>2</sup> mm h<sup>-1</sup> (i.e., 100 km x 100 km x 2 mm h<sup>-1</sup>) at least once during the lifetime.

