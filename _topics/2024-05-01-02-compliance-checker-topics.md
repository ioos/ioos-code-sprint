---
number: 2
title: Compliance Checker Topics
pis:
  - Rob Cermak
  - Filipe Fernandes
  - Callum Rollo
contributors:
  - TBD
github: ioos/ioos-code-sprint/issues/40
slack:
  - code-sprint-2024
  - erddap
  - python
breakout:
  - TBD
year: 
  - 2024
---

Design, implementation and assessment of the OceanGlider (OG) 1.0 metadata standard on the IOOS
Compliance Checker and related tools.  This may include general initial implementation of a compliance
checker plugin.  The plugin may require some initial examples for testing.  Related topics include
addressing current issues with the compliance checker and existing plugins.  Topics may include and are
not necessarily limited to adding and improving CF standards checking and curation of example datasets
for testing.  

Another goal is to increase community engagement with the compliance checker and other IOOS repositories.
The general task would be to form a uniform set of github documentation to guide user interatation with
the IOOS repositories.  Examples may be and are not limited to development of uniform set of issue templates,
code of conduct, etc.

**Expected Outcomes:**

 * Improved documentation for Compliance Checker and plugins
 * Squash current issues for Compliance Checker and plugins
 * Design and implementation of OG 1.0 plugin
 * Ensure working pytest suites
 * Form and utilize a uniform pool of example datasets
 * General github documentation for facilitation of community engagement within IOOS repositories.

**Skills required:**

Python programming, basic understanding of NetCDF files and associated metadata standards (CF, ACDD, etc).

**Difficulty:**

Easy to Moderate

**Relevant links:**

Compliance Checkers
 * [https://github.com/ioos/compliance-checker](https://github.com/ioos/compliance-checker)
 * [https://github.com/ioos/compliance-checker-web](https://github.com/ioos/compliance-checker-web)
 * [https://github.com/ioos/cc-plugin-glider](https://github.com/ioos/cc-plugin-glider)
 * [https://github.com/ioos/cc-plugin-ncei](https://github.com/ioos/cc-plugin-ncei)
 * [https://github.com/ioos/cc-plugin-ugrid](https://github.com/ioos/cc-plugin-ugrid)
   * [https://github.com/pp-mo/ugrid-checks](https://github.com/pp-mo/ugrid-checks)

Metadata Standards
 * [Ocean Glider 1.0 User Manual Github](https://github.com/OceanGlidersCommunity/OG-format-user-manual)
 * [Ocean Glider 1.0 User Manual Github.io](https://oceangliderscommunity.github.io/OG-format-user-manual/)
 * [NGDAC NetCDF File Format Version 2](https://ioos.github.io/glider-dac/ngdac-netcdf-file-format-version-2.html)
 * [CF Metadata Conventions](https://cfconventions.org/)

Vocabularies
 * [NERC](https://vocab.nerc.ac.uk/collection/)
 * GliderDAC Compliance Checker Plugin Authority Tables
   * [NCEI Institution Table](https://gliders.ioos.us/ncei_authority_tables/institutions.txt)
   * [NCEI Project Table](https://gliders.ioos.us/ncei_authority_tables/projects.txt)
   * [NCEI Instrument Table](https://gliders.ioos.us/ncei_authority_tables/instrument.txt)
   * [NCEI Platform Table](https://gliders.ioos.us/ncei_authority_tables/platforms.txt)
   * [NCEI Sea Name Table](https://www.ncei.noaa.gov/data/oceans/ncei/vocabulary/seanames.xml)

Example Datasets
 * [pyoceans:pocean-core Test Data](https://github.com/pyoceans/pocean-core/releases/download/2024.04/test_data.zip)
 * [CF Conventions List of Examples](https://cfconventions.org/cf-conventions/cf-conventions.html#List_of_Examples)
 * [NECI NetCDF Templates](https://www.ncei.noaa.gov/netcdf-templates)
 * [ERDDAP unit test examples](https://github.com/ERDDAP/erddapTest)
 * [Ocean Glider Example Files](https://github.com/OceanGlidersCommunity/OG-format-user-manual/tree/main/og_format_examples_files)
 * [test.opendap.org](http://test.opendap.org/)

References
 * [OG Format User Manual Discussion #165](https://github.com/OceanGlidersCommunity/OG-format-user-manual/discussions/165)
 * [OG Format User Manual Discussion #92](https://github.com/OceanGlidersCommunity/OG-format-user-manual/discussions/92)
 * [OG Format User Manual PR #172](https://github.com/OceanGlidersCommunity/OG-format-user-manual/pull/172)
