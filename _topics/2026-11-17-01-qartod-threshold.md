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
  - Room 2, 5
year: 
  - 2026
---

Develop an AI/ML-based tool to assist in setting station-specific QA/QC thresholds for sensors (including water level, shore stations, etc.). The tool would establish thresholds and possibly quantify the confidence of those values. The tool could utilize historical sensor timeseries data, sensor characteristics, sensor metadata, nearby stations, and site-specific context, if available. 

## **Expected Outcomes**

- Prototype AI/ML tool generating station-specific QARTOD thresholds
- Documented workflow that can be used with the prototype tool to test it on multiple stations

## **Skills required**

- Python
- Machine learning / AI
- Familiarity with QARTOD tests

## **Expertise**

Intermediate

## **Topic Lead(s)**

Aaron Mau, Marta Wolfshorndl

## **Relevant links**

* <https://ioos.noaa.gov/project/qartod/>
* https://github.com/ioos/ioos_qc/pull/272
* https://github.com/ioos/ioos_qc/pull/273

Somewhat related:
* <https://cdn.ioos.noaa.gov/attachments/2025/AI-Enabled%20Water%20Level%20Data%20Quality%20Control.pdf>

## **Functioning Prototype**

See the `mlqc` branch until the PR is merged.
[Example notebooks here](https://github.com/ioos/ioos_qc/tree/mlqc/docs/source/examples).

## **Workflow**

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

## **Updates**

**Day 1 update:**
* We convened and got on the same page. We started discussing the history of the issue and ways that we could use reproducible ML algorithms on the data.
* Initialized our branch, created a Slack channel for development, and started setting up our environments for more intense work in the following days.

**Day 2 update:**
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

**Day 3 update:**
* Ran yesterday's code on additional datasets - providing insight to some storm impacts and detection methods. Led to good conversations.
* Created a PR that expanded the autogeneration of limits to the `spike_test`, including enhanced plotting functionality.
* Reset the defaults for `climatology` and `gross_range` tests, such that the defaults most closely align with what we think the operators should be doing.
* Refactored yesterday's code to more comfortably live in `utils.py` and `plotting.py`.
* Created two new notebooks in `docs/source/examples` which highlight how to automatically generate quality control limits and how to easily get started.
* Looped in additional support to the Slack channel, discussing bigger picture questions and some of the preferred coding practices.

We also discussed the following next step items:
* Expanding on the sprint
  * Running the autogen on other tests, such as `rate_of_change` and `flatline` tests.
  * Think about the autogen QC as an entire workflow - could the users chain *all* the required and recommended tests together with statistically-derived tests, rather than static "legacy" limits?
  * Worth following up with the QARTOD steering committee and mailing lists - the #qartod channel has not been particularly active even though networking suggests new operators don't know what to do, or are reinventing the wheel.
* Issues
  * Plotting from notebooks can be homogenized or extracted to `plotting.py`
  * Create a "helpers" repository for QARTOD, such that `ioos_qc` can focus on the tests, and `helpers` can contain the helpful documentation and tools
  * Potential bug in the spike algorithm, and there are other methods that could be compared
* Helpers - a potentially new repository
  * Live limit visualization tool with gauges and bars and toggles that show how QC changes on data.
  * More examples from diverse hardware and regional environments
  * ID bad and good phenomenon in datasets -> What are some norms, and when do you flag these scenarios?
  * Extract many of the non-essential functions in `ioos_qc` that may be bloating it, such that `ioos_qc`'s install is minimal.

