
# Weather Forecasts for Machine Learning Post-processing 

### A Repository for the Rapid Development of Machine Learning Post-Processing Methods. 

### Associated Publications: 
--- 

 -- If you are using this data, please cite: --

1) Towards Implementing AI Post-processing in Weather and Climate: Proposed Actions from the Oxford 2019 Workshop.


2) Chapman, William E.; Lerch, Sebastian; Kirkwood, Charlie; Subramanian, Aneesh C.; Matsueda, Mio; Haupt, Sue E. (2020). Postprocessing model V 1.0. In Data for: Towards Implementing AI Post-processing in Weather and Climate: Proposed Actions from the Oxford 2019 Workshop. UC San Diego Library Digital Collections. https://doi.org/10.6075/J08S4NDM


## Downloading the Data: 

<pre><code> wget : .... location of Data on UCSD servers.
</code></pre>

See the \emph{notebooks} folder jupyter notebooks for easy ingest of a specific data set. 

##### File Organization: 
The file download will be a folder called "All_Zarr", which contains 21 seperate Zarr file structures. 

## Data Descriptions: 

This data set contains 5 seperate forecasted weather fields along with the verifying values, all packaged in a clean format. 
The descriptions are as follows. The notebooks contain simple ways to download and methods to benchmark against. The goal is for rapid development of statistical methods to improve our global weather forecasts. The forecasts include: 


#### 1.1 MJO Ensemble Forecasts

Files are from 8 modeling centers [CMA, CMC, CPTEC, ECMF, JMA, KMA, NCEP, UKMO] 

The zarr path has the type All_Zarr/MJO_XXXXzar where XXXX represents the center (e.g. ./All_Zarr/MJO_ECMWFzar )

We also include a database of climate variability modes identified from six separate operational weather forecast models for more than a decade worth of forecasts. The Madden-Julian Oscillation (MJO - Madden and Julian 1977, 1994), a dominant intraseasonal mode of variability in the Tropics and a significant source of predictability globally on subseasonal timescales, has been identified using statistical techniques on forecast variables. We use the zonal winds at 850 hPa, 200 hPa and outgoing longwave radiation from both the forecast models and observations to diagnose the MJO and evaluate its forecast skill. 

#### 1.2 PNA Ensemble Forecasts

Files are from 8 modeling centers [CMA, CMC, CPTEC, ECMF, JMA, KMA, NCEP, UKMO]

The zarr path has the type All_Zarr/PNA_XXXXzar where XXXX represents the center (e.g. ./All_Zarr/MJO_ECMWFzar )


Similarly, the Pacific North American pattern which is a large-scale weather pattern over the Pacific Northwest region has been identified using the geopotential height field (Wallace and Gutzler 1981) in both observations and model forecasts. These datasets are provided as benchmark datasets for training post-processing algorithms to improve forecasts of these large scale modes of variability and concomitantly subseasonal forecast skill of other related weather patterns.  


#### 1.3 Global Forecast System Integrated Vapor Transport 
Files are from the NCEP GFS model, and has 3 forecast lead times (006hr,048hr,168hr) 
The zarr path has the type All_Zarr/GFSIVT_FXXX_zarr where XXXX represents forecast lead (e.g. ./All_Zarr/GFSIVT_F048_zarr )


GFS predictions (Moorthi et al., 2001) at a 0.5‐degree horizontal spatial resolution on 64 vertical levels for daily 0000 and 1200 UTC model initializations are utilized to calculate the forecasted magnitude of integrated vapor transport (IVT). IVT is a combined momentum and thermodynamic metric which integrates specific humidity and u and v components of the wind speed from 1000 to 300 hpa. Here we present three forecast lead times of 1-day, 2-days, and 1 week from 2006 to 2018. This includes ~8000 data ﬁelds for every forecast lead time or ~24,000 forecasted ﬁelds across all lead times. The region of interest spans coastal North America and the Eastern Paciﬁc from 180°W to 110°W longitude, and 10°N to 60°N latitude. IVT from the National Aeronautics and Space Administration's Modern-Era Retrospective Analysis for Research and Applications version 2 (MERRA-2) reanalysis is also packaged and serves as ground truth data. MERRA-2 data are resolved on a 0.625 x 0.5 degree grid and interpolated to 21 pressure levels between 1000 and 300 hpa for IVT calculation (Gelaro et al. 2017; McCarty et al., 2016). For consistency, GFS predictions are then remapped to this grid resolution using a 1st and second order conservative remapping scheme. Further details can be found in Chapman et al 2019. 
 
#### 1.4 ECMWF Two-Meter Temperature Ensemble over Germany 
Files are from the ECMWF 51 member ensemble, and contains 048hr forecast's of T2m 

The zarr path has the type All_Zarr/ECMWFt2m_zar

 
An example of short-range forecasts and verifying observations is a dataset of temperature observations at 537 stations over Germany and predictors derived from the ECMWF ensemble prediction system from 2007 to 2016. Predictors are mean and standard deviation of 48-hour ahead 50-member ECMWF ensemble forecasts of temperature and optimally interpolated to station locations. The corresponding observations (valid at 00UTC) are obtained from surface synoptic observations stations operated by the German weather service. Details (including a list of predictors) are available in Rasp and Lerch (2018).
 
#### 1.5 UK surface road conditions
Files are from the UKMO ensemble, and contains road temperature conditions in the UK 

The zarr path has the type All_Zarr/Hrly_RoadForecast_zarr

 
This dataset contains numerical weather prediction forecasts from all models in the UK Met Office's Road Surface Temperature (MORST) forecasting system, along with corresponding road network temperature observations from Highways England. Data are provided for four random sites (location undisclosed) and spans 98 days from mid-December 2018 to late March 2019 on an hourly forecast lead basis from 0 to 168 hours. Ground truth data are provided by the road surface temperature observed at the road network weather station for the concurrent forecast time. The dataset spans 2342 forecasting hours for each of the four sites. Spanning all lead times and owing to the fact that a multitude of forecasts are made for each hour by the time it is observed, the dataset spans over 1.34 million forecasts.


Acronym key:
---
T2m  = Two Meter Temperature 

MJO = Madden Julian Oscillation

PNA = Pacific North American Pattern 

GFS = Global Forecast System 

CMA = China Meteorological Administration

CMC = Canadian Meteorological Center

CPTEC = Center for Weather Forecasting and Climate Studies (Brazil)

ECMWF = European Center for Medium Range Weather Forecasting 

JMA = Japanese Meteorological Agency

KMA = Korean Meteorological Agency

NCEP = National Center for Environmental Prediction

UKMO = United Kingdom Meteorological Office





