# Spatial distribution of the snow as a function of global warming levels

## Scientific context
Snow is classified as a "fast" climate variable because it responds quickly to temperature fluctuations, like sea ice, but this is less the case for other variables in the climate system, such as precipitation. In this regard, its future evolution is crucial to monitor. To anticipate these developments, we use climate models that simulate trajectories based on socioeconomic pathways (SSPs) combining social development scenarios and emissions scenarios. Historically, projections were based on these scenarios, but a new approach is to group these scenarios in terms of global warming levels to obtain more reliable results for climate policies. For example, the Paris Agreement's objectives are expressed in terms of global warming levels that should not be exceeded, and this is precisely what changes the vision. This new approach was incorporated into the latest IPCC report, dating from 2021, the old approach still prevailing in 2013.

## Internship objectives
The main objective of my internship was to produce maps of the spatial distribution of snow as a function of global warming levels, in a single map because to our knowledge it had not been produced before, from a multi-model average from the CMIP6 database.
Two main questions emerge from this problematic : is it scientifically justified to produce a multi-model mean ? and, Does that provide reliable insights ? 

## Instructions on how to proceed

### General informations

In a blank environment on Jupyter Notebook, you can access all the folders present in this GitHub repository. There are two main folders: "module" and "notebooks."

The "module" folder contains three files: libs.py (where all the libraries are stored) and functions.py (where all the functions used in this work are grouped). Notebooks execute this module at the beginning to avoid calling all the libraries each time. You can open these files for more details if needed.
The "notebooks" folder contains all the notebooks necessary to reproduce this work. These are numbered from 1 to 7, and it is important to follow this order. The names of the notebooks describe their contents.
Finally, if you are more interested in this work, you can find the report in the "report" folder, along with all the associated figures.

### Data

All the input and output data are provided and can be found in the shared storage of OpenReproLab, in the folder named "Data_LaurieV."

### Instructions to reproduce the work - Use of notebooks

Please follow the steps in order, as each step produces intermediate results that are useful for the next part of the analysis. If you only want to reproduce certain notebooks, the intermediate data is already provided.

1) The first step is to run the first notebook (1) to create output data. Verify that you obtain 25 different files at the end of the procedure. Note that this code was produced by my supervisor and I did not modify anything.

2) The second step is to convert all the useful files to a single, consistent reference grid for future comparisons. For this, use notebook (2). Run all the cells and verify that new folders have been created.

3) For these new files, it is necessary to recompute the areacella (the area of each grid cell), which is a very important variable for calculating the spatial extension of the snow. For this, run notebook (3).

4) A supplementary step is necessary for a model that does not simulate snow in Greenland: the IPSL model. It is important to add snow data for this model using the sftgif mask (ice-land fraction) so that all models have the same characteristics. For this, use notebook (4).

5) At this stage, we will have two output files for the IPSL model: one named "IPSL-CM6A-LR_SW_reprojete.nc" (the older one) and another named "IPSL-CM6A-LR2_SW_reprojete.nc" (the newer one). You need to manually delete the older file and rename the newer one to match the old name (simply remove the number "2").

6) Now that all the models are consistent, we can visualize and compute the monthly snow extent for each model during the reference period (1995-2014). Snow extent values will be stored in a dictionary and exported to a CSV format for further analysis. For this, use notebook (5).

7) Once the dictionary is extracted, we can compare these values to real observation data of the snow in order to detect which models performed well and which ones performed poorly. To do this, run notebook (6). This step calculates the differences between observations and simulations, and each model will be scored using two scoring functions. The resulting file will also be saved.

8) Until this point, the analysis has been done individually for each model. Since the main objective is to use a multi-model mean, the last step consists of calculating this mean. From the multi-model mean, we can produce final maps of seasonal snow extent as a function of global warming levels, weighted by the scores. To perform this, use notebook (7).