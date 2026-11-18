---
number: 1
title: Station Specific QA/QC Thresholds for Sensor Stations
pis:
  - (@klankers)
  - (@martaw22)
contributors:
  - (@KarinaKh)
  - (@tborgfeldt)
github: ioos/ioos-code-sprint/issues/87
slack:
  - code-sprint-2026-mlqc
breakout:
  - Room 2
year: 
  - 2026
---

Develop an AI/ML-based tool to assist in setting station-specific QA/QC thresholds for sensors (including water level, shore stations, etc.). The tool would establish thresholds and possibly quantify the confidence of those values. The tool could utilize historical sensor timeseries data, sensor characteristics, sensor metadata, nearby stations, and site-specific context, if available. 

**Expected Outcomes**

- Prototype AI/ML tool generating station-specific QARTOD thresholds
- Documented workflow that can be used with the prototype tool to test it on multiple stations

**Skills required**

- Python
- Machine learning / AI
- Familiarity with QARTOD tests

**Expertise**

Intermediate

**Topic Lead(s)**

Aaron Mau, Marta Wolfshorndl

**Relevant links**

* <https://cdn.ioos.noaa.gov/attachments/2025/AI-Enabled%20Water%20Level%20Data%20Quality%20Control.pdf>
* <https://ioos.noaa.gov/project/qartod/>

**Functioning Prototype**

TBD

**Workflow**

Tasks:

1. Find example training datasets
2. Choose potential models
3. Create training workflow and reproduce results
4. Scale up to more datasets

Deliverables:

1. `auto_thresh` module in `ioos_qc`
   * This includes example model weights and coeffs, training code to export coeffs
2. Walkthrough Jupyter notebook for building your own model
   * In `docs/examples`

**Updates**

Day 2 update:
* We ran a ML processor on our example data, but had a realization that we don't need ML at all for the `gross_range_test`. It's a common practice to assign the global range limits to a certain number of standard deviations if there is no obvious literature that describes the expected annual conditions for the data.
* We re-evaluated what we thought would be required.
  * Operators still don't quite know what to set their ranges to for the `gross_range_test`, `climatology_test`, or `spike_test`. These can be satisfied by:
    * Fail parameters being specified by sensor manufacturers
    * Suspect parameters being identified statistically for the data
  * Furthermore, the `climatology_test` configuration has historically very hard to define and can be daunting for new operators or data access centers.
    * Can we, using ML clustering methods, identify different periods of time within the data (including "seasonal" or repeating trends)
    * Run our statistical bounds during each period and build a `climatology` configuration through reproducible statistics.
* We (including Claude) put together a new module, `build_limits.py`, which seeks to address this.
  * Use `k-means` to identify different periods by number of specified temporal bins (ignores annual trends, better for shorter datasets), shared regimes (like supporting storms in both winter and summer), and "seasons" (annual trends within a specified resolution summed over multiple years).
  * Pass in the `auto_thresh` function with a specified number of standard deviations to permit
  * Generate the climatology config, using terminology consistent with `IOOS_QC`'s existing code (`period`, for example, to support `weekofyear`)
 * We passed it over our previous training set and it successfully builds statistically-reproducible bounds and configs for the `gross_range` and `climatology_test`s.

Objectives tomorrow will to be to continue to refine the code and build some documentation. Ideally, we'll have the following defaults:
* Cluster my data "seasonally", such that I can build a climatology for every January, or every Spring, or every 01-15 to 02-20.
  * "Seasonal" limits are the best defined for nrt data or streams, where the current time is known. This is most intuitive for individuals that are not experts in the region.
* Get averages for those specified ranges with a standard deviation of 3.
* Return the climatology and support plotting for the user to see what the configuration looks like.
* Make `plot_limits` more generic, such that a user can more easily visualize premade configurations for the climatology and gross range
* Investigate `spike_test`
* Run again with remote participant, submitting data with known storm data
* Finalize a Jupyter notebook that can live in the documents of IOOS QC to demonstrate the workflow

