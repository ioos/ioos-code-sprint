---
number: 2
title: OBIStools-style QC library in Python
pis:
  - Jon Pye
contributors:
  - Stace Beaulieu
  - Mathew Biddle
  - Pieter Provoost
github: ioos/ioos-code-sprint/issues/7
slack: 
  - biological-data
breakout:
  - Biology/Ecology
---

Coming off the heels of the OBIS-USA/IOOS/MBON/OTN Bio Data Mobilization workshop, we realized there is a gap in the toolchain for Python folks who would like to prepare data for inclusion as DarwinCore archives into OBIS, esp via OBIS-USA. These functions are defined and implemented already in R, as part of the iobis/obistools package. The job would seem to be porting iobis/obistools functionality to a fresh package in Python. The existing obis-qc package could be imported by this package to include any useful checks currently implemented there, but an extension of obis-qc to accept arbitrary data sources is not the preferred method of solving this problem.

**Expected Outcomes:**

A series of QC checks are codified in [https://github.com/iobis/obistools](https://github.com/iobis/obistools) that users can apply against their biological presence data to ensure its fitness for inclusion in a DarwinCore archive. A small group of Python users would like to have this functionality native to Python. There is a iobis/obis-qc package, but this is meant for checking against already-accepted OBIS data, and presumes the obistools QC has already happened. there is a client pyobis that is for retrieving already registered data. A Pythonic obistools seems to be the missing part of the toolset. additionally, there have been some advancements in user-friendliness via a RShiny application over at [EMODNet/EMODnetBiocheck](https://github.com/EMODnet/EMODnetBiocheck)

**Skills required:**

Python and R knowledge, some experience with porting functionality from one language to the other welcomed.

**Difficulty:**

Moderate

**Team:**
Jon Pye - Ocean Tracking Network(sprint lead)
Kyle Wilcox - Axiom Data Science
Ryan Gosse - Ocean Tracking Network
Simon Beauvillier - Observatoire Global du St. Laurent (author)
Germain Sauve - Observatoire Global du St. Laurent (author)
Naomi Tress - Ocean Tracking Network
Mathew Biddle - IOOS
Abby Benson

**Activities:**

Code for running checks donated by the OGSL team and adapted from the BioData Mobilization workshop was re-implemented by the Sprint team as a Python module. A repository was created under the CIOOS namespace to host pyobistools. The module [https://github.com/cioos-siooc/pyobistools](https://github.com/cioos-siooc/pyobistools) has implemented much of the low-level QC functionality from the iobis/obistools package, including functions for checking fields and formats for both Occurrence Core-formatted files as well as an extension to check Event Core files and their extension Occurrence files. 

Taxonomic checks, field checks, date and spatial coordinate format checks, as well as on_land and depth checks are implemented using GeoPandas in place of R's sp package and leveraging the same xylookup service as is used in obistools, a service that OBIS maintains

Linting and CI have been implemented to ensure the package is more readily maintained and extended going forward.

Testing for the package is being deployed to mirror the tests currently implemented on iobis/obistools. Translation of strings used in the module is included in a file but is not yet in the YAML format required to be implemented with python-i18n. A milestone will be created for that work, to be completed post-Sprint.

Maintenance of this package will be undertaken by its authors and the Sprinters from the Ocean Tracking Network, under their CIOOS partnership. More functionality will be added over time in an effort to more accurately mirror functionality in iobis/obistools. When a core set of functionality is tested and ready, registration with PyPI/Conda will follow.

**Relevant links:**

* [https://github.com/iobis/obistools](https://github.com/iobis/obistools)
* [https://github.com/iobis/obis-qc](https://github.com/iobis/obis-qc)
* [https://github.com/iobis/pyobis](https://github.com/iobis/pyobis)
