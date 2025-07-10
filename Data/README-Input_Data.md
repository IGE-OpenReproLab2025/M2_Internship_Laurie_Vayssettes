## Retrieve Input Data

Most of the input data used in this project are stored on the spirit platform of the ESPRI server at IPSL. Access to this platform requires authorization and is available only via a terminal session.

---

To retrieve **historical snow cover (`snc`)** data:

`cd /bdd/CMIP6/CMIP/{institution}/{model}/historical/{realization}/LImon/snc/{grid}/latest`

To retrieve **historical near-surface air temperature (`tas`)** data, simply replace `LImon/snc` with `Amon/tas` in the path:

`cd /bdd/CMIP6/CMIP/{institution}/{model}/historical/{realization}/Amon/tas/{grid}/latest`

Replace {institution}, {model}, {realization}, and {grid} with the appropriate values for each model.

For the realization, always choose the closest available to `r1i1p1f1`.

The {grid} is often gr or gn, depending on the model.

You must repeat this operation for each model individually.

Access Scenario Projections (SSP5-8.5):

To retrieve **future snow cover (`snc`) projections** under the SSP5-8.5 scenario:

`cd /bdd/CMIP6/ScenarioMIP/{institution}/{model}/ssp585/{realization}/LImon/snc/{grid}/latest`

For temperature projections (`tas`), again replace `LImon/snc` with `Amon/tas`:

`cd /bdd/CMIP6/ScenarioMIP/{institution}/{model}/ssp585/{realization}/Amon/tas/{grid}/latest`

You can change the scenario (`sp585`) to another one (e.g., `ssp126`, `ssp245`) if needed for additional experiments.


## Description of Input Data

### Snow reference data

The snow cover data used in this study come from the Rutgers University Global Snow Lab dataset (https://climate.rutgers.edu/snowcover/). The data have been regridded to a 1°×1° resolution and cover only the Northern Hemisphere. For this project, we use data from the period 1995–2014, based on the IPCC reference period.

---

### Near-Surface Air Temperature (`Amon-tas`) – Historical

This folder contains monthly near-surface air temperature (`tas`) data from various models, covering the **historical period 1850–2014**. 

- **Temporal resolution**: monthly  
- **Units**: Kelvin (`K`)  
- **Spatial coverage**: global

---

### Snow Cover Fraction (`LImon-snc`) – Historical

This folder includes monthly snow cover fraction (`snc`) data covering the 18500–2014 period, for different models.

- **Temporal resolution**: monthly  
- **Units**:  
  - Most models: fraction (values between `0` and `1`)  
  - Some models: percentage (values between `0` and `100`)

This variable represents the fraction of the land surface covered by snow and is used in conjunction with masks to focus analysis on continental areas.

---

### Mask Data

These mask variables are essential to correctly interpret and spatially filter the climate data from different models. They allow us to apply land/ocean/ice masks and convert grid-based data into physical units like square kilometers.

#### • `areacella` and `pseudo-areacella`

These folders contain grid cell area data (in `m²`) for different climate models. Although the variable is the same, it differs slightly depending on the model resolution. These files are used to convert binary or fractional values into physical areas (e.g. `m²` or `km²`), which is essential for spatial integration or aggregation.

#### • `sftlf` and `pseudo-sftlf`

These folders provide the **land surface fraction** for each model. The values are binary:
- `1` = land  
- `0` = ocean

This mask is particularly useful when we want to analyze or visualize variables only over continental regions.

#### • `sftgif` and `pseudo-sftgif`

These folders contain the **land ice surface fraction** (glacier areas). Values are also binary:
- `1` = ice  
- `0` = other (land or ocean)

This mask is used to exclude glacier-covered areas from certain analyses if necessary.

---

### Near-Surface Air Temperature (`Amon-tas`) – Scenario `SSP5-8.5`

This folder contains monthly near-surface air temperature (`tas`) data from various models under the `SSP5-8.5` scenario, covering the **future period 2015–2100**. This scenario was chosen because it represents the most extreme projected emissions pathway (the “worst case” scenario), allowing us to assess high-impact climate outcomes.

- **Temporal resolution**: monthly  
- **Units**: Kelvin (`K`)  
- **Spatial coverage**: global

---

### Snow Cover Fraction (`LImon-snc`) – Scenario `SSP5-8.5`

This folder includes monthly snow cover fraction (`snc`) data under the same `SSP5-8.5` scenario (2015–2100), for different models.

- **Temporal resolution**: monthly  
- **Units**:  
  - Most models: fraction (values between `0` and `1`)  
  - Some models: percentage (values between `0` and `100`)

This variable represents the fraction of the land surface covered by snow and is used in conjunction with masks to focus analysis on continental areas.
