---
layout: page
title: "Tracking algorithms"
---

# Overview of Tracking algorithms

|  *Name*     | *Spatial segmentation* | *Temporal linking method* | *Merging/splitting treatment* | *Programming language* | *Link* | 
|----------|----------|----------|----------|----------|----------|
| [PyFLEXTRKR]({{ site.baseurl }}/pyflextrkrkr)    | 2D detect-and-spread cold core: Tb < 225 K, spread to Tb < 241 K     | Overlap (0.5)    | Yes    | Python     |  |
| [simpleTrack]({{ site.baseurl }}/simpletrack)    | Threshold-connectivity Tb < 241 K     | Overlap (0.6)     | Yes     | Python     |  |
| [TAMS])({{ site.baseurl }}/tams)    | Contour (polygon) Tb < 241 K     |  Overlap (0.5)    | Yes |  Python     |  |
| [DL + TempestExtreme]({{ site.baseurl }}/dl_tempest_extreme)    | Convolutional neural network (U-Net) Trained with PyFLEXTRKR data | Overlap (uses TempestExtremes) (0.5)    | No    | Python, C++     |  |
| [tobac]({{ site.baseurl }}/tobac)    | Water-shedding Tb < 241 K     | Parcels, propagation speed    |  Yes   | Python     |  |  
| [KFyAO]({{ site.baseurl }}/kfyao)     | Threshold-connectivity Tb < 241 K     | Overlap and Kalman filter (0.15)    | No    | Matlab    |  |
| [MOAAP]({{ site.baseurl }}/moaap)    | 3D water-shedding     | Overlap (one gridcell)     | Yes    | Python     |  |
| [TOOCAN]({{ site.baseurl }}/toocan)    | 3D region growing (space + time) Tb dilation from 190 K to 241 K, +2 K/step   | Data     | No     | C     |  |
| [TIMPS]({{ site.baseurl }}/timps)    | 2D detect-and-spread multi-thresholds with outer Tb < 241 K   | Overlap (max overlap)   | No   | Python, C++     |  |
| [ATRACKS]({{ site.baseurl }}/atracks)  |  multi-thresholds with outer Tb < 241 K, Contour (polygon) Tb < 241 K | Overlap (0.25)    | No     | Python     |  | 



