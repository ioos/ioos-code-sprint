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


