# UNH_PSdeployment_S21

This project contains the data collected by the University of New Hampshire (UNH) Coastal Processes Lab for a field experiment in September 2021. The data was collected at Wallis Sands Beach in Rye, NH. The main instrument utilized was the Pressure Stick (PS), which is a fully autonomous pressure-profiling instrument. The PS contains eight micro-controlled, time-synced TE Connectivity MS5837 Bar02 pressure and temperature sensors distributed along a 70 cm distance to measure pressure throughout the water column and into the sediment bed. Global Positioning System (GPS) surveys of the beach profile were also completed before and after the experiment, and the survey data is also included in this project. Data of the offshore wave conditions as measured by the [Jeffrey's Ledge waverider buoy (station 44098) from the National Data Buoy Center (NDBC)](https://www.ndbc.noaa.gov/station_page.php?station=44098) is given here as well.

This dataset is presented in the manuscript, "Field Observations of Vertical Pressure Head Gradients in a Nearshore Sediment Bed; A Case for Momentary Liquefaction" (Marry & Foster, XXXX) which has been submitted to the Journal of Geophysical Research: Oceans in 2023. 

## Dataset files
A description of each data file is given below:

### Pressure Stick Data
1. Folder UNH_PSdataS21_Raw (or UNH_PSdataS21.mat)

    This folder (or file) contains the raw data from the Pressure Stick for the full deployment time (September 10th 2021 22:55:00 - September 12th 7:15:00). Note this file is large so you will need to use a shared link to get to the location of the file to then download the data file.
    - UNH_PSdataS21_P.txt (or P) = raw pressure (mbar, [2056516x8] vector) 
    - UNH_PSdataS21_dt.txt (or dt) = datetime ([2056516x1] vector)
    - UNH_PSdataS21_dn.txt (or dn) = serial datenumber ([2056516x1] vector)
    - UNH_PSdataS21_T.txt (or T) = temperature (deg C, [2056516x8] vector)
    - UNH_PSdataS21_Pd.txt (or Pd) = pressure head (m, [2056516x8] vector)
    - UNH_PSdataS21_z.txt (or z) = sensor elevations (m, [1x8] vector, negative values in the sediment bed, sensor 1 is the top sensor closest to the circuitry/top of the instrument)
    
2. UNH_PSdataS21_10min.csv (.mat)

    This file contains data from the Pressure Stick, where the values have been calculated for 10-minute segments of data throughout the full deployment time (September 10th 2021 22:55:00 - September 12th 7:15:00). Used to plot Figures 2 and 6 in (Marry & Foster, XXXX).
    - h = average water depth for each 10-minute segment (m, [194x1] vector) 
    - chunk_mean = mean datetime value for each 10-minute segment ([194x1] vector)
    - Hsig = significant wave height for each 10-minute segment (m, [194x1] vector)
    - S = wave skewness for each 10-minute segment ([194x1] vector)
    - A = absolute value of wave asymmetry for each 10-minute segment ([194x1] vector)
    - WavePeriods = average wave period for each 10-minute segment (s, [194x1] vector)
    - WaveHeights = average wave height for each 10-minute segment (m, [194x1] vector)
    - dPddz_W50 = median of the maximum vertical pressure gradient of each wave for each sensor pair in the sand for each 10-minute segment ([194x4] vector)
    - dPddt_W50 = median of the maximum time derivative of pressure for each wave for each 10-minute segment (m/s, [194x1] vector)
    - dPddt_W50N = median of the maximum time derivative of pressure for each wave divided by the maximum time derivative of pressure for a theoretical sinusoidal wave with the same wave height and wave period for each 10-minute segment ([194x1] vector)
    - S_W50 = median of the maximum Sleath parameter of each wave for each 10-minute segment ([194x1] vector)
    - Hoverh = depth normalized wave height (H/h) for each 10-minute segment ([194x1] vector)
    - dPddz_WM50 = median of the maximum vertical pressure gradient of all sensors in the sand for each wave for each 10-minute segment ([194x1] vector)
    - dPddzcrit = range of critical vertical pressure gradient values to induce momentary liquefaction as defined by Mory et al. (2007) ([2x1] vector) 
            
3. UNH_PSdataS21_2min.csv (.mat)

    This file contains data from the Pressure Stick, where the values have been calculated for a two-minute time series of data (September 11th 2021 2:33:00 - 2:35:00). Used to plot Figures 4 and 5 in (Marry & Foster, XXXX).
    - dt2 = datetime for the two-minute time series ([2121x1] vector) 
    - Pd2 = pressure for all sensors for the two-minute time series (m, [2121x8] vector)
    - Pd_hydro2 = expected hydrostatic pressure for all sensors for the two-minute time series (m, [2121x8] vector)
    - sensorselev = sensor elevations for the two-minute time series (m, [1x8] vector)
    - dtSliceW1 = datetime values for the instantaneous vertical pressure profiles of the first selected wave in the two-minute time series ([1x6] vector)
    - dtSlice_indexW1 = indices of the datetime values for the instantaneous vertical pressure profiles of the first selected wave in the two-minute time series ([1x6] vector)
    - dtSliceW2 = datetime values for the instantaneous vertical pressure profiles of the second selected wave in the two-minute time series ([1x6] vector)
    - dtSlice_indexW2 = indices of the datetime values for the instantaneous vertical pressure profiles of the second selected wave in the two-minute time series ([1x6] vector)
    - dtSliceW3 = datetime values for the instantaneous vertical pressure profiles of the third selected wave in the two-minute time series ([1x6] vector) 
    - dtSlice_indexW3 = indices of the datetime values for the instantaneous vertical pressure profiles of the third selected wave in the two-minute time series ([1x6] vector)
    - dtSliceW4 = datetime values for the instantaneous vertical pressure profiles of the fourth selected wave in the two-minute time series ([1x6] vector) 
    - dtSlice_indexW4 = indices of the datetime values for the instantaneous vertical pressure profiles of the fourth selected wave in the two-minute time series ([1x6] vector)
    - dPddz2 = vertical pressure gradient for all sensor pairs for the two-minute time series ([2121x7] vector)
    - dPddt2 = time derivative of pressure for the two-minute time series ([2121x1] vector)
    - dPddzcrit = range of critical vertical pressure gradient values to induce momentary liquefaction as defined by Mory et al. (2007) ([2x1] vector)
    - Pe = excess pore pressure for all sensors for the two-minute time series (m, [2121x8] vector)

4. UNH_PSdataS21_Waves.csv (.mat)

    This file contains data from the Pressure Stick, where the values have been calculated for each individual wave throughout the full deployment time (September 10th 2021 22:55:00 - September 12th 7:15:00). Used to plot Figures 7, 8, and 9 in (Marry & Foster, XXXX).
    - dPddzcrit = range of critical vertical pressure gradient values to induce momentary liquefaction as defined by Mory et al. (2007) ([2x1] vector)
    - WaveHeightsWbW = wave heights for each individual wave ([4628x1] vector)
    - WavePeriodsWbW = wave periods for each individual wave ([4628x1] vector)
    - HoverhWbW = depth normalized wave height (H/h) for each individual wave ([4628x1] vector)
    - dPddt_W = maximum time derivative of pressure for each individual wave (m/s, [4628x1] vector)
    - dPddz_WM = maximum vertical pressure gradient of all sensor pairs in the sand for each individual wave ([4628x1] vector)
    - dPddz_W = maximum vertical pressure gradient of each sensor pair for each individual wave ([4628x7] vector)
    - S_W = maximum Sleath parameter value for each individual wave ([4628x1] vector)
    - hW = water depth for each individual wave (m, [4628x1] vector)
    - PercentLiq_Hh = percent of waves that exceed the momentary liquefaction threshold from Mory et al. (2007) for each sensor pair in the sand binned by the depth normalized wave height (H/h) (%, [4x5] vector)
    - PercentLiq_S = percent of waves that exceed the momentary liquefaction threshold from Mory et al. (2007) for each sensor pair in the sand binned by the Sleath parameter (%, [4x4] vector)
    - dPddt_WO = maximum time derivative of pressure for a theoretical sinusoidal wave with the same wave height and wave period as each measured individual wave in the deployment time (m/s, [4628x1] vector)
    - dPddt_WN = maximum time derivative of pressure normalized by (pi*H)/T for each individual wave ([4628x1] vector)
    - dPddt_WON = maximum time derivative of pressure for a theoretical sinusoidal wave normalized by (pi*H)/T for each individual wave ([4628x1] vector)
    - S_WO = maximum Sleath parameter for a theoretical sinusoidal wave for each individual wave ([4628x1] vector)            

### GPS Data
1. UNH_GPS_S21_20210908.txt (.pos) (.mat) 

    This file contains data from a GPS survey taken on September 8th 2021 as the pre-deployment survey. Used to plot Figure 3 in (Marry & Foster, XXXX). 
    - GPST = time stamp of the survey sample 
    - latitude = latitude in degrees
    - longitude = longitude in degrees
    - height = elevation height, relative to WGS84/ellipsoidal in meters
    - Q = quality of the data point. Q = 1 is a 'good' data point, Q = 2 is an 'okay' data point, and Q > 2 are 'bad' data points. 
    - ns = Number of satellites
    
2. UNH_GPS_S21_20211026.txt (.pos) (.mat)

    This file contains data from a GPS survey taken on October 26th 2021 as the post-deployment survey. Used to plot Figure 3 in (Marry & Foster, XXXX). 
    - GPST = time stamp of the survey sample 
    - latitude = latitude in degrees
    - longitude = longitude in degrees
    - height = elevation height, relative to WGS84/ellipsoidal in meters
    - Q = quality of the data point. Q = 1 is a 'good' data point, Q = 2 is an 'okay' data point, and Q > 2 are 'bad' data points. 
    - ns = Number of satellites

### Waverider Buoy (NDBC station 44098) Data
1. NDBC_44098_JeffreysLedgeBuoy_S21.txt (.mat)

    This file contains offshore wave data from [Jeffrey's Ledge waverider buoy (station 44098) from the National Data Buoy Center (NDBC)](https://www.ndbc.noaa.gov/station_page.php?station=44098) throughout the full deployment time (September 10th 22:56:00 - September 12th 7:26:00). Used in (Marry & Foster, XXXX). Please see [Description of Measurements](https://www.ndbc.noaa.gov/measdes.shtml) for a discussion of each of the variables in this file.
    
DOI: v1.1.0: https://doi.org/10.5281/zenodo.8161628
     v1.0.0: https://doi.org/10.5281/zenodo.7796469
