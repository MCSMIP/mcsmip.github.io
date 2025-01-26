---
layout: page
title: "MOAAP"
parent: "Tracking algorithms"
order: 7 
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


The Multi-Object Analysis of Atmospheric Phenomenon algorithm (MOAAP, Prein et al. (2023)) can track 14 atmospheric phenomena including MCSs. Here, MOAAP version 1.1 was used, which detects anvil clouds that are colder than 241 K. Next, we use a watersheds algorithm to segment large cloud areas into individual MCSs by identifying the location of overshooting tops that are at least 225 km apart. This distance is a tuning parameter and is derived from taking twice the radius of a circular cloud shield that has an area of 40,000 km2. This water-shedding step is performed for each hour by spreading out radially around the identified overshoots. The resulting cloud areas are connected in time by searching for maximum overlaps of individual cloud shields from one hour to the next. If multiple overlapping objects are detected the ones with the largest overlap are connected and others are treated as splits or mergers. The characteristics of the resulting objects are assessed and the entire track of the object is labeled as MCS if it meets the criteria described in Section 2c.