---
number: 2
title: OBIStools-style QC library in Python
pis:
  - Jon Pye
  - Stace Beaulieu
  - Mathew Biddle
  - Pieter Provoost
contributors:
  - 
github: ioos/ioos-code-sprint/issues/7
slack: 
  - biological-data
---

Coming off the heels of the OBIS-USA/IOOS/MBON/OTN Bio Data Mobilization workshop, we realized there is a gap in the toolchain for Python folks who would like to prepare data for inclusion as DarwinCore archives into OBIS, esp via OBIS-USA. These functions are defined and implemented already in R, as part of the iobis/obistools package. The job would seem to be porting iobis/obistools functionality to a fresh package in Python. The existing obis-qc package could be imported by this package to include any useful checks currently implemented there, but an extension of obis-qc to accept arbitrary data sources is not the preferred method of solving this problem.

**Expected Outcomes:**

A series of QC checks are codified in [https://github.com/iobis/obistools](https://github.com/iobis/obistools) that users can apply against their biological presence data to ensure its fitness for inclusion in a DarwinCore archive. A small group of Python users would like to have this functionality native to Python. There is a iobis/obis-qc package, but this is meant for checking against already-accepted OBIS data, and presumes the obistools QC has already happened. there is a client pyobis that is for retrieving already registered data. A Pythonic obistools seems to be the missing part of the toolset. additionally, there have been some advancements in user-friendliness via a RShiny application over at [EMODNet/EMODnetBiocheck](https://github.com/EMODnet/EMODnetBiocheck)

**Skills required:**

Python and R knowledge, some experience with porting functionality from one language to the other welcomed.

**Difficulty:**

Moderate

**Relevant links:**

* [https://github.com/iobis/obistools](https://github.com/iobis/obistools)
* [https://github.com/iobis/obis-qc](https://github.com/iobis/obis-qc)
* [https://github.com/iobis/pyobis](https://github.com/iobis/pyobis)