---
layout: page
title: "Tracking algorithms"
---

# Overview of Tracking algorithms

<table>
    <tr>
        <td>Name</td>
        <td>Spatial segmentation</td>
        <td>Temporal linking method</td>
        <td>Merging/splitting treatment</td>
        <td>Programming language</td>
        <td>Link</td>
        <td></td>
    </tr>
    <tr>
        <td>[PyFLEXTRKR]({{ site.baseurl }}/pyflextrkrkr)</td>
        <td>2D detect-and-spread cold core: Tb &lt; 225 K, spread to Tb &lt; 241 K</td>
        <td>Overlap (0.5)</td>
        <td>Yes</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[simpleTrack]({{ site.baseurl }}/simpletrack)</td>
        <td>Threshold-connectivity Tb &lt; 241 K</td>
        <td>Overlap (0.6)</td>
        <td>Yes</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[TAMS])({{ site.baseurl }}/tams)</td>
        <td>Contour (polygon) Tb &lt; 241 K</td>
        <td>Overlap (0.5)</td>
        <td>Yes</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[DL + TempestExtreme]({{ site.baseurl }}/dl_tempest_extreme)</td>
        <td>Convolutional neural network (U-Net) Trained with PyFLEXTRKR data</td>
        <td>Overlap (uses TempestExtremes) (0.5)</td>
        <td>No</td>
        <td>Python, C++</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[tobac]({{ site.baseurl }}/tobac)</td>
        <td>Water-shedding Tb &lt; 241 K</td>
        <td>Parcels, propagation speed</td>
        <td>Yes</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[KFyAO]({{ site.baseurl }}/kfyao)</td>
        <td>Threshold-connectivity Tb &lt; 241 K</td>
        <td>Overlap and Kalman filter (0.15)</td>
        <td>No</td>
        <td>Matlab</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[MOAAP]({{ site.baseurl }}/moaap)</td>
        <td>3D water-shedding</td>
        <td>Overlap (one gridcell)</td>
        <td>Yes</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[TOOCAN]({{ site.baseurl }}/toocan)</td>
        <td>3D region growing (space + time) Tb dilation from 190 K to 241 K, +2 K/step</td>
        <td>Data</td>
        <td>No</td>
        <td>C</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[TIMPS]({{ site.baseurl }}/timps)</td>
        <td>2D detect-and-spread multi-thresholds with outer Tb &lt; 241 K</td>
        <td>Overlap (max overlap)</td>
        <td>No</td>
        <td>Python, C++</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>[ATRACKS]({{ site.baseurl }}/atracks)</td>
        <td>multi-thresholds with outer Tb &lt; 241 K, Contour (polygon) Tb &lt; 241 K</td>
        <td>Overlap (0.25)</td>
        <td>No</td>
        <td>Python</td>
        <td></td>
        <td></td>
    </tr>
</table>


 241 K     | Overlap and Kalman filter (0.15)    | No    | Matlab    |  |
 | [MOAAP]({{ site.baseurl }}/moaap)    | 3D water-shedding     | Overlap (one gridcell)     | Yes    | Python     |  |
 | [TOOCAN]({{ site.baseurl }}/toocan)    | 3D region growing (space + time) Tb dilation from 190 K to 241 K, +2 K/step   | Data     | No     | C     |  |
 | [TIMPS]({{ site.baseurl }}/timps)    | 2D detect-and-spread multi-thresholds with outer Tb < 241 K   | Overlap (max overlap)   | No   | Python, C++     |  |
 | [ATRACKS]({{ site.baseurl }}/atracks)  |  multi-thresholds with outer Tb < 241 K, Contour (polygon) Tb < 241 K | Overlap (0.25)    | No     | Python     |  |

