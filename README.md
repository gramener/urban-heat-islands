# Urban_Heat_Islands_demo

This repository is the Urban Heat Island Project demo, made for the purpose of PyCon Submissions as well as Geopython Submissions for the year 2022.

## Setup the environment

Use the environment.yml file to install required packages.

```bash
conda env create -f environment.yml
```
## Steps involved in the project

'''
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
'''