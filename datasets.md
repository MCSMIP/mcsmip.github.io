---
layout: page
title: "Data Access and Policies"
order: 2
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

Data Access for MCS catalogues, processed DYAMOND data, Citation, and Authoship.

# MCSMIP: DYAMOND Data Access

## 1. Catalogue Data Access
* Full access is available for all MCSMIP participants and collaborators of MCSMIP participants.
* Public access will be granted after publication of overview papers.
* **Tier 1 catalogues for DYAMOND datasets** ([NERSC Globus](https://app.globus.org/file-manager?origin_id=a7c4e644-ee68-40e1-a7f3-0258c7680605&origin_path=%2F))

## 2. Citations

* All papers using MCSMIP data or analysis should cite the [JGR-A paper](https://mcsmip.github.io/publications/).
* All papers using MCSMIP data catalogues should cite the DOI numbers for catalogues and source data.
* Data will be published on Zenodo
* DOIs:
	* MCSMIP DYAMOND Data DOI: **TBD**

## 3. Authorship
* Authors are free to choose their co-authors and collaborators, however the MCSMIP project must be acknowledged.
* Below is suggested text for a typical “Acknowledgments” section:

MCSMIP is a grass-root community effort comprising international researchers from universities, laboratories, and agencies. The co-chairs and committee members include Zhe Feng, L. Ruby Leung, Andreas Prein, Julia Kukulies, Kelly Núñez Ocasio, Zachary Moon, Fengfei Song, Jinyan Song, Wenhao Dong, Manikandan Rajagopal, and John Mejia. Detailed information about the MCS catalogue developers is available on the [MCSMIP website](https://mcsmip.github.io/). This effort is supported by the U.S. Department of Energy Office of Science, Biological and Environmental Research (BER) as part of the Regional and Global Model Analysis program area through the Water Cycle and Climate Extremes Modeling (WACCEM) scientific focus area. 

---

# Description of Standardized DYAMOND Datasets

The description of directories and file names below include `[]` that denotes variable names, for example:

> [phase]: Summer, Winter
> 
> [source]: OBS, NICAM, SCREAM
> 
> [tracker]: PyFLEXTRKR, TOOCAN, tobac

## MCS mask files

* MCS mask files (0.1° × 0.1°): 
	* `/mcs_mask/[phase]/[tracker]`
	* Animations: 
		* `/mcs_mask/animations/[tracker]/[tracker]_[source]_[tracker]_[region].mp4`
* MCS mask files (0.25° × 0.25°):
	* `/mcs_mask_0.25deg/[tracker]/[tracker]`

## Tracks

MCS track files (statistics) are also stored in netCDF format, generally following the format used by PyFLEXTRKR.

* MCS track files:
	* `/mcs_stats/[tracker]/[tracker]/mcs_stats_[phase]_[source].nc`

* MCS frequency and precipitation map files:
	* `/mcs_stats/[tracker]/[tracker]/mcs_rainmap_[phase]_[source].nc`

* MCS environmental track files (2D):
	* `/mcs_stats/[tracker]/[tracker]/mcs_tracks_[phase]_[source]_intqv_2d.nc`

* MCS environmental track files (1D, spatially averaged):
	* `/mcs_stats/[tracker]/[tracker]/mcs_tracks_[phase]_[source]_intqv_1d.nc`

* MCS Tb/rain rate histogram files:
	* `/mcs_stats/[tracker]/[tracker]/tb_rainrate_hist_[phase]_[source].nc`

* MCS collocated rain rate vs. PW files:
	* `/mcs_stats/[phase]/[tracker]`

## Global DYAMOND data 

All DYAMOND data used in the MCSMIP paper have been regridded to a common **0.1° × 0.1°** (lat/lon grid) at **1 hourly** resolution. Certain variables are also available at 0.25° × 0.25° (regridded to ERA5 resolution).

* Combined OLR and precipitation data (single file for each model and each phase [Summer/Winter]): 
	* `/OLR_Precipitation_combined/olr_pcp_[phase]_[source].nc`

* Combined OLR and precipitation data (0.25° × 0.25°): 
	* `/OLR_Precipitation_combined_0.25deg/olr_pcp_[phase]_[source].nc`

* Precipitable Water (PW) regridded to 0.25° × 0.25°: 
	* `/Environments_0.25deg/[phase]_[source]_intqv.nc`

* 2D environmental variables regridded to 0.1° × 0.1°: 
	* `/Environments/[phase]/[phase]_[source]_[variable].nc`

## Observation data

Global geostationary infrared brightness temperature (Tb) and GPM IMERG precipitation data are stored in the same location as the DYAMOND OLR and precipitation data:

* Combined Tb and precipitation data:
	* IMERG V06B: `/OLR_Precipitation_combined/olr_pcp_[phase]_OBS.nc`
	* IMERG V07B: `/OLR_Precipitation_combined/olr_pcp_[phase]_OBSv7.nc`

* GPM DPR Ku-band swath rain rate data:
	* Native resolution: `/GPM_DYAMOND/DPR/src_grid`
	* Regridded to IMERG (0.1° × 0.1°): `/GPM_DYAMOND/DPR/regrid_0.1deg/[year]/`
	* Regirdded to ERA5 (0.25° × 0.25°): `/GPM_DYAMOND/DPR/regrid_0.25deg/[year]/`

* GPM DPR Ku-band MCS rain rate histogram data 
	* At 0.1° × 0.1°: `/GPM_DYAMOND/DPR/regrid_0.1deg/[year]/rainrate_hist_[phase]_DPR_[tracker].nc`
	* At 0.25° × 0.25°: `/GPM_DYAMOND/DPR/regrid_0.25deg/[year]/rainrate_hist_[phase]_DPR_[tracker].nc`
