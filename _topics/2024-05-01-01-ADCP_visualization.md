---
number: 1
title: Visualization of ADCP Data in ERDDAP
pis:
  - Felimon Gayanilo
contributors:
  - Sandeep Jilla
github: ioos/ioos-code-sprint/issues/45
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2024
---

Some NOAA IOOS RAs had been compiling ocean current data from Acoustic Doppler Current Profiler (ADCP). ADCPs can be mounted on: (1) vessels (downward looking), (2) mid-water or glider mounted (upward and downward looking), or bottom mounted (upward looking). The Gulf of Mexico Coastal Observing System (GCOOS) is receiving ADCP data from various oil and gas platforms or from Mobile Offshore Drilling Units (MODUs). The number of bins (depth range) varies depending on the depth of the water column. GCOOS is receiving hourly compilation of data from 50 active ADCPs mounted on 46 station locations. The ADCP data for the Gulf of Mexico can be accessed from GCOOS ERDDAP [https://erddap.gcoos.org/erddap/search/index.html?page=1&itemsPerPage=1000&searchFor=NTL%20wmo-42](https://erddap.gcoos.org/erddap/search/index.html?page=1&itemsPerPage=1000&searchFor=NTL%20wmo-42).

The general task is to develop a configurable Python package that can be imported to read and plot ADCP data. Although a 2D plot will help assess the quality of the readings, validating 2D hydrodynamic simulations, or can be applied to structural engineering problems, a 3D plot of the currents will be most useful in helpful in analyzing the 3D hydrodynamics/ocean currents in the area.

**Expected Outcomes:**
* Python-based package the can be imported to display 2D or 3D ocean current plots from ADCPs or similar data types.
* 3D plots with a time-slider to manually or automatically view plots for different time frames for all depths on one station

**Skills required:**

Python programming, netCDF understanding, accessing ERDDAP service

**Difficulty:**

Easy to Moderate

**Relevant links:**
* GCOOS ERDDAP for NTL Stations: [https://erddap.gcoos.org/erddap/search/index.html?page=1&itemsPerPage=1000&searchFor=NTL%20wmo-42](https://erddap.gcoos.org/erddap/search/index.html?page=1&itemsPerPage=1000&searchFor=NTL%20wmo-42)
* ADCP Principles of Operation: [https://www.comm-tec.com/Docs/Manuali/RDI/BBPRIME.pdf](https://www.comm-tec.com/Docs/Manuali/RDI/BBPRIME.pdf)
* NDBC ADCP profile plots: [https://www.ndbc.noaa.gov/faq/adcp.shtml](https://www.ndbc.noaa.gov/faq/adcp.shtml)
* Python stick plots: [https://notebook.community/rsignell-usgs/notebook/stickplot](https://notebook.community/rsignell-usgs/notebook/stickplot)

**Functioning Prototype**

TODO

**Workflow**
* read netCDF data from ERDDAP services
* compute plotting configurations, and
* display the 2D or 3D plots
