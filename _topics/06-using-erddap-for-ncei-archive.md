---
number: 6
title: Using ERDDAP in the IOOS RA/DAC archival pipelines
pis:
  - Mathew Biddle
contributors:
  - Bob Simons
  - John Relph
github: ioos/ioos-atn-data/issues/28
slack:
  - erddap
breakout:
  - ERDDAP
---

Currently, the IOOS Regional Associations (RA's) and Functional Data Assembly Centers (DAC's) rely heavily on using the 
ERDDAP data serving system as one mechanism for sharing data. IOOS has published a [metadata profile](https://ioos.github.io/ioos-metadata/) 
which contains dataset attribution guidelines and examples to help the US IOOS community publish datasets in netCDF and 
other related data formats in an interoperable manner.

In their current state, most of the RA's and DAC's are generating netCDF files for archival at NCEI in accordance with 
the [NCEI netCDF templates](https://www.ncei.noaa.gov/netcdf-templates). In some cases they are using ERDDAP to generate 
the appropriate files and share them with NCEI via a Web Accessible Folder (WAF). This can be a duplicative process to 
the IOOS Metadata Profile recommendations or other DAC recommendations.

This project will explore using ERDDAP as a tool/mechanism to generate the appropriate data files and metadata and share 
them with NCEI for long-term archival purposes. With the hopes that we can streamline data generation and transmission 
to NCEI for the RAs and DACs (and a larger community of ERDDAP users).

**Expected Outcomes:**

Identify a path forward for using ERDDAP to build packages for archival at NCEI.

**Skills required:**

Python, Java (if ERDDAP dev. is needed), RA DMAC infrastructure background

**Difficulty:**

Moderate

**Relevant links:**

* [https://github.com/ioos/ioos-atn-data/issues/28](https://github.com/ioos/ioos-atn-data/issues/28)
* [https://ioos.github.io/ioos-metadata/](https://ioos.github.io/ioos-metadata/)
* [https://www.ncei.noaa.gov/netcdf-templates](https://www.ncei.noaa.gov/netcdf-templates)
