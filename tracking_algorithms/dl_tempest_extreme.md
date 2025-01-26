---
layout: page
title: "DL + TempestExtreme"
parent: "Tracking algorithms"
order: 8
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



A deep learning model (DL), U-Net (Ronneberger et al., 2015), was trained to detect MCSs within hourly ERA5 reanalysis (Hersbach et al., 2020) spanning 2004-2019 over North America. The input variable is top-of-atmosphere net thermal radiation converted to Tb for consistency with MCSMIP protocol. ERA5 MCS labels were created using the PyFLEXTRKR algorithm Feng et al. (2023) with a 3-percentile precipitation threshold. During training, only samples that contained MCSs were used to account for class imbalance issues. The training, validation, and evaluation sets contained 48747, 8124, and 24375 samples respectively. The input was standardized using training set statistics only, which were also used for the validation and evaluation sets. Two classes were output by U-Net, “no MCS object” and “MCS object,” run through a softmax equation, resulting in output that can be interpreted as a probability. U-Net hyperparameters were selected following a hyperparameter grid search and were 0.0001 learning rate, Adam optimizer, random vertical flips (50%), cross-entropy loss function, 32 batch size, and 12 epochs. The trained U-Net was then applied to DYAMOND. Tb was converted to top net thermal radiation and standardized using the previously derived training data mean and standard deviation. The software is open source at: https://github.com/mariajmolina/ML-extremes-mcs. 

To connect the U-Net-derived MCS features over time, we utilized the DetectBlobs and StitchBlobs algorithms from TempestExtremes (TE; Ullrich et al. (2021)). DetectBlobs identifies features in a single time slice based on a specified threshold; in this case, an MCS probability threshold derived from the U-Net output, where probabilities exceeding 3% designate candidate features. These candidates are then represented as binary masks. StitchBlobs tracks these features over time, assigning each connected feature a unique global identifier. The tracking algorithm uses a forward-backward search that treats the combined "2D space + 1D time" domain as a single 3D object, enabling the detection of both merging and splitting events. Candidate MCSs are classified as the same feature if they have a temporal overlap exceeding 50% and persist for 4 or more hours. To comply with the common set of criteria outlined in Section 2c, a post-processing script was developed (https://github.com/mg-albright/post-process-dl-mcsmip).