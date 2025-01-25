---
layout: page
title: "Tracking algorithms"
---

# Overview of Tracking algorithms

|  **Name**     | **Spatial segmentation** | **Temporal linking method** | **Merging/splitting treatment** | **Programming language** | **Link** | 
|-------------|------------------------|---------------------------|-------------------------------|------------------------|--------|
| [PyFLEXTRKR]({{ site.baseurl }}/pyflextrkrkr)    | 2D detect-and-spread cold core: Tb<225K, spread to Tb < 241 K     | Overlap (0.5)    | Yes    | Python     | [https://github.com/FlexTRKR/PyFLEXTRKR](https://github.com/FlexTRKR/PyFLEXTRKR) |
| [simpleTrack]({{ site.baseurl }}/simpletrack)    | Threshold-connectivity Tb<241K     | Overlap (0.6)     | Yes     | Python     | [https://github.com/thmstein/simple-track](https://github.com/thmstein/simple-track) |
| [TAMS]({{ site.baseurl }}/tams)    | Contour (polygon) Tb<241K     |  Overlap (0.5)    | Yes |  Python     |   [https://github.com/knubez/TAMS](https://github.com/knubez/TAMS/tree/main) |
| [DL + TempestExtreme]({{ site.baseurl }}/dl_tempest_extreme)    | Convolutional neural network (U-Net) Trained with PyFLEXTRKR data | Overlap (uses TempestExtremes) (0.5)    | No    | Python, C++     | [ https://github.com/mariajmolina/ML-extremes-mcs](https://github.com/mariajmolina/ML-extremes-mcs) |
| [tobac]({{ site.baseurl }}/tobac)    | Water-shedding Tb<241K     | Parcels, propagation speed    |  Yes   | Python     | [https://github.com/tobac-project/tobac](https://github.com/tobac-project/tobac) |  
| [KFyAO]({{ site.baseurl }}/kfyao)     | Threshold-connectivity Tb<241K     | Overlap and Kalman filter (0.15)    | No    | Matlab    |  |
| [MOAAP]({{ site.baseurl }}/moaap)    | 3D water-shedding     | Overlap (one gridcell)     | Yes    | Python     | [https://github.com/AndreasPrein/MOAAP](https://github.com/AndreasPrein/MOAAP) |
| [TOOCAN]({{ site.baseurl }}/toocan)    | 3D region growing (space + time) Tb dilation from 190 K to 241K, +2 K/step   | Data     | No     | C     | [https://toocan.ipsl.fr/](https://toocan.ipsl.fr/) |
| [TIMPS]({{ site.baseurl }}/timps)    | 2D detect-and-spread multi-thresholds with outer Tb<241K   | Overlap (max overlap)   | No   | Python, C++     |  |
| [ATRACKS]({{ site.baseurl }}/atracks)  |  multi-thresholds with outer Tb<241K, Contour (polygon) Tb<241K | Overlap (0.25)    | No     | Python     | [https://doi.org/10.5281/zenodo.7025989](https://doi.org/10.5281/zenodo.7025989) | 



