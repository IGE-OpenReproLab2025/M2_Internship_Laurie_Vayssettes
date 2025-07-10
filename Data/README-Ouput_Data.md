## Description of Output Data

All output files described below were generated during the analysis and are available in either `netCDF` or `CSV` format, depending on the file type.

---

### `SnowWarming_1995_2014`

This folder contains all the files created by the first notebook. These files use the period `1995–2014` as a **reference baseline**, meaning that warming levels are relative to this period (e.g., `+0.5°C` is relative to `1995–2014`).

Each file contains two variables:  
- **`sncbin`**: snow cover area fraction as a function of latitude (`I`), longitude (`J`), **warming level (`K`)**, and **month (`L`)**. It is not time-based but warming-based.  
  - `K` ranges from `-0.5°C` to `+5°C`, with a step of `0.25°C` → 23 levels.  
  - `L` ranges from `1` to `12` (months).

- **`Limit`**: represents snow area as a function of **snow cover thresholds (`K`)** rather than warming levels.  
  - Here, `K` has 5 values:  
    - `1` = 10%  
    - `2` = 25%  
    - `3` = 50%  
    - `4` = 75%  
    - `5` = 90%  
  - For example, `K = 1` means snow is considered present when it exceeds 10% coverage.

All values are expressed as **fractions** (between `0` and `1`).

---

### `Snow_hist`

This folder contains the **interpolated historical snow cover files**, derived from the original `historical-LImon-snc` input data.  
- All data characteristics are preserved.  
- Only the grid has changed: all files are now aligned to a **common grid**.

---

### `Snow_SW_1995_2014`

This folder contains the same data and variables as `SnowWarming_1995_2014`, but all files have been **regridded** to a **common spatial grid** for comparability across models.

---

### `Sftlf`

This folder groups together all `sftlf` and `pseudo-sftlf` files (land fraction masks), but now interpolated onto the same grid.

---

### `Sftgif`

Same as above, but for `sftgif` and `pseudo-sftgif` files (land ice fraction masks), interpolated and grouped into a single folder.

---

### `Areacella_recalcule`

This folder contains recalculated `areacella` files for each model.  
- These were recomputed using the `CDO` tool based on the regridded snow data.  
- Units: square meters (`m²`).  
- These represent the area of each grid cell in the new common grid.

---

All folders from 1 to 6 contain data in **`netCDF` format**.

---

### `Snow_cover_per_model`

This CSV file contains the **average monthly snow-covered area** for each model during the reference period `1995–2014`, expressed in **square kilometers (`km²`)**.

---

### `Scores_modeles`

This CSV file contains three columns:
- **Absolute error** (in `km²`)
- **Score (exponential function)** (unitless)
- **Score (Gaussian function)** (unitless)

These metrics are computed for each model and **sorted in ascending order** of performance.

---

## Strategy of Conservation

The output data will **not be preserved in the long term** and will therefore **not be published on Zenodo** or any other long-term open repository.

This is because:
- The output may change if the input data are updated or corrected in future CMIP6 database releases.
- Recomputing the output ensures consistency with the most recent versions of the inputs.

In the **short term**, the output files are useful for analyzing how snow cover responds to global warming levels and for visualization or comparison purposes.

## License

These data produced by VAYSSETTES Laurie, in 2025 are licensed under a Creative Commons Attribution 4.0 International License (https://creativecommons.org/licenses/by/4.0/).
You are free to:
– Share – copy and redistribute the material in any medium or format
– Adapt – remix, transform, and build upon the material for any purpose, even commercially.
Under the following terms:
– Attribution – You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.