# Urban_Heat_Islands_demo

This repository is the Urban Heat Island Project demo, made for the purpose of PyCon Submissions as well as Geopython Submissions for the year 2022.

## Setup the environment

Use the environment.yml file to install required packages.

```bash
conda env create -f environment.yml
```
## Data Samples
https://archive.org/details/@sumedhghatage?tab=uploads&and[]=mediatype%3A%22software%22
Make sure you arrange the data in the given folder structure
## Steps involved in the project

There are total 6 notebooks involved which takes into consideration
Data preprocessing, Indices calculation, Spatial Merging, zonal statistics and Spatial regression model


1. [Calculate satellite variables](step0_Calculation_satellite_variables.ipynb) pre-processing Landsat 8 data.
2. [Convert to time-based grids](step1_add-time-to-grids.ipynb)
3. [Add non-satellite variables to grids](step2_add-attrs-to-grids.ipynb)
4. [Merge satellite and non-satellite variables](step3_merge-attrs-time.ipynb)
5. [Calculate derived variables](step4_entropy_bbc.ipynb): Shannon's entropy and building block coverage
6. [Create spatial regression model](step5_spatial-regression-statsmodels.ipynb)

## Quick Information Guide

### Satellite Imagery Data - Landsat 8

With the presence of changing atmospheric conditions, there are images that get hampered
due to the presence of the cloud cover. We must filter out those images on the basis of the
scene cloud cover.

Scene cloud cover is nothing but the presence of cloud cover in the area of interest. The
below image shows one of such scenarios.

The images selected for the modeling purpose through visual inspection and the metadata
information for the image using [USGS Earth Explorer](https://earthexplorer.usgs.gov/)

### Zonal Statistics and Aggregation

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

### Spatial Regression

Spatial regression methods allow us to account for dependence between
observations, which often arises when observations are collected from points
or regions located in space.

Regression (and prediction more generally) provides us a perfect case to examine how
spatial structure can help us understand and analyze our data. Usually, spatial structure
helps models in one of two ways. The first (and most clear) way space can have an impact
on our data is when the process generating the data is itself explicitly spatial
