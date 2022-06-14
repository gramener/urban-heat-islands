# Urban_Heat_Islands_demo

This repository is the Urban Heat Island Project demo, made for the purpose of PyCon Submissions as well as Geopython Submissions for the year 2022.

## Setup the environment

Use the environment.yml file to install required packages.

```bash
conda env create -f environment.yml
```
## Steps involved in the project
There are total 6 notebooks involved which takes into consideration 
Data preprocessing, Indices calculation, Spatial Merging, zonal statistics and Spatial regression model


    1.Step0_Calculation_Satellite_Indices.ipynb 
        Notebook Which Performs the landsat8 data preprocessing and Indices calculation for AOI.

    2. step1_add-time-to-grids.ipynb
        Working with the satellite data time component to convert it into grid geojson.

    3. step2_add-attrs-to-grids.ipynb
        adding the attribute information to the grids made in step one

    4. step3_merge-attrs-time.ipynb
        This step helps to merge the attributes and calculated indices information with the yearly timestamps   

    5. step4_entropy_bbc.ipynb
        Calculation of Shannon's entropy and building block coverage for each grid at a specific year.

    6. step5_spatial-regression-statsmodels.ipynb
        Calculation of Shannon's entropy and building block coverage for each grid at a specific year.


## Quick Information Guide

### Satellite Imagery Data - Landsat 8
With the presence of changing atmospheric conditions, there are images that get hampered
due to the presence of the cloud cover. We must filter out those images on the basis of the
scene cloud cover.

Scene cloud cover is nothing but the presence of cloud cover in the area of interest. The
below image shows one of such scenarios.

The images selected for the modeling purpose through visual inspection and the metadata
information for the image using [USGS Earth Explorer](https://earthexplorer.usgs.gov/)

### Zonal Statistics and Aggregation:

Zonal statistics calculates or performs the statistics with the values of the value raster. Then
get the statistics values for each zone based on the zone raster. A zone is defined as all the
cells that have the same value in the input (the discontinuous cells of same value are
accepted to be a zone).

Zonal Statistic as Table shows the result in Table instead of raster.
Zone raster defines the shape, value and position of the zone, and the input value raster
provides the original data for calculation.

Here the number of zones provided based on the grid size. The grid size was created using
supermercado by mapbox at zoom level 18 (which is approx. 100m Grid )
All the zonal statistics for landsat data are calculated using the method above. The
Morphological factors were then aggregated on the basis of each grid using mean, minimum
and maximum values.

The zonal statistics for each year is calculated for each year from 2013 to 2020 for the
summer months (From May to September every year.)