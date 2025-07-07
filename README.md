# Spatial distribution of the snow as a function of global warming levels

## Scientific context
Snow is classified as a "fast" climate variable because it responds quickly to temperature fluctuations, like sea ice, but this is less the case for other variables in the climate system, such as precipitation. In this regard, its future evolution is crucial to monitor. To anticipate these developments, we use climate models that simulate trajectories based on socioeconomic pathways (SSPs) combining social development scenarios and emissions scenarios. Historically, projections were based on these scenarios, but a new approach is to group these scenarios in terms of global warming levels to obtain more reliable results for climate policies. For example, the Paris Agreement's objectives are expressed in terms of global warming levels that should not be exceeded, and this is precisely what changes the vision. This new approach was incorporated into the latest IPCC report, dating from 2021, the old approach still prevailing in 2013.

## Internship objectives
The main objective of my internship was to produce maps of the spatial distribution of snow as a function of global warming levels, in a single map because to our knowledge it had not been produced before, from a multi-model average from the CMIP6 database.
Two main questions emerge from this problematic : is it scientifically justified to produce a multi-model mean ? and, Does that provide reliable insights ? 

## Instructions on how to proceed

1) The first step consists to run the first notebook (1) to create output data : verify that you obtain 25 different files at the end of the procedure. Note that this code was produced by my supervisor and I did not modify anything.

2) The second step consists to convert all the useful files on a single and same reference grid to allow future comparisons. For that, use the notebook (2). Run all the cells and verify that new folders have been created.

3) For these new files, it is necessary to recompute the areacella (which corresponds to the area of each grid cell), very important variable to calculate the spatial extension of the snow. For this, you can run the notebook (3).

4) A supplementary step is necessary for a model which do not simulate the snow in the Greenland : the IPSL's one. It is important to add it for this model, thanks to the sftgif mask (ice land fraction) to have the same characteristics for all the models. For this, use the notebook (4).

5) At this stage, we have two output files for IPSL model. One named "IPSL-CM6A-LR_SW_reprojete.nc" (the oldest) and another named "IPSL-CM6A-LR2_SW_reprojete.nc" (the new). You have to delete manually the oldest one and rename the new one by the name of the old (you just have to delete the number 2).

6) Now all the models are similar, so we can visualize and compute the monthly snow extent for each model during the reference period (1995-2014). Snow extent values will be stored in a dictionnary extracted on a csv format, for further analysis. For that, use the notebook (5).

7) When the dictionnary is extracted, we can compare these values to those of real data observations of the snow to detect models which made a good simulation of the snow and those that have a poor simulation. For that, you have to run the notebook (6).
From the calculation of the differences between observations and simulations, each model will be scored by two scoring functions and this new file will be also extract.

8) Since here, analysis have been done individually for each model. As the problematic is focused on the use of a multi-model mean, this last step consist to realize this mean.
From this multi-model mean we can produce final maps of the seasonal snow extension in function of global warming levels by weighting with the scores. To realize this mean and create the maps, use the notebook (7).