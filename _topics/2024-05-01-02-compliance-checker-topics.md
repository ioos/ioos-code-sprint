---
number: 2
title: Compliance Checker Topics
contributors:
  - Benjamin Adams
  - Rob Cermak (topic lead)
  - Filipe Fernandes
  - Callum Rollo
github: ioos/ioos-code-sprint/issues/40
slack:
  - compliance-checker
  - code-sprint-2024
breakout:
  - compliance-checker
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
 * [NECI NetCDF Templates](https://www.ncei.noaa.gov/netcdf-templates)

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

---

**Work Completed**

An Ocean Glider 1.0 plugin is largely operational with three specification
tests. These tests can be combined with CF-1.8 at present with CF-1.9 and
CF-1.10 coming soon! The plug-in is available from this
[repository](https://github.com/uw-farlab/cc-plugin-og) which will be
eventually migrated into the IOOS organizational repository.

 * 10 closed [pull requests](https://github.com/ioos/cc-plugin-glider/pulls?q=label%3Aioos-code-sprint-2024+) for cc-plugin-glider
 * 11 closed [pull requests](https://github.com/ioos/compliance-checker/pulls?q=label%3Aioos-code-sprint-2024+) for compliance-checker 

**Future Actions**

 * Activate CF-1.9 and CF-1.10 in compliance checker for use in the OG-1.0 plugin.  For now
   the OG-1.0 plugin can utilize CF-1.8.
 * Finish off CF-1.9/CF-1.10 work
 * Work on CF-1.11 in coordination with UK Met effort.  This will retire the UGRID plugin.
   * Changes from [CF-1.8 to CF-1.9](https://github.com/cf-convention/cf-conventions/compare/1.8.0...1.9.0#diff-3b9c470edad8a09f463987db632803f1ecc22561199fa5771745ad472a62e0ee)
   * Changes from [CF-1.9 to CF-1.10](https://github.com/cf-convention/cf-conventions/compare/1.9.0...v1.10.0#diff-3b9c470edad8a09f463987db632803f1ecc22561199fa5771745ad472a62e0ee)
   * Changes from [CF-1.9 to CF-1.11](https://github.com/cf-convention/cf-conventions/compare/1.9.0...v1.11.0#diff-3b9c470edad8a09f463987db632803f1ecc22561199fa5771745ad472a62e0ee)
   
   * Plugin for AI? Wait for further mapping and reconcilation of AI Ready
     specifications to current IOOS metadata template and see what needs to be done.

   * Central repository for example datasets? No.  The compliance checker repository will
     curate for convienence only pointers to examples of interest: ERDDAP, NCEI, IOOS
     "golden standard" and Ocean Glider repositories.  Utilization of python pooch is the
     recommended method of access.


