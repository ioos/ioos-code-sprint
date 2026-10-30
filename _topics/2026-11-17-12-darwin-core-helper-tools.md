---
number: 12
title: Darwin Core helper tools
pis:
  - (@7yl4r)
  - (@mathewbiddle)
contributors:
  - TBD
github: ioos/ioos-code-sprint/issues/67
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2026
---

This project explores the cutting edge of software that helps researchers publish taxonomic occurrence data. 

-------------------------------------

Better biodiversity assessments start with better data. 
How can we combine observations of when, where, and what researchers are seeing in the biota around us?

We need Findable, Accessible, Interoperable, and Reusable (FAIR) data to empower cross-dataset exploration.
What can software do to help researchers publish FAIR data?

AI can work at many times the speed of a human on digitized information but standards of alignment, responsibility, and ethics have not yet been established.
What is the role of AI in the process of bridging physical ecosystems and FAIR data repositories like the Ocean Biodiversity Information System (OBIS)?

-------------------------------------

### Software product ideas :

This project may span multiple software prototypes.
Some prototype ideas are outlined below.


#### AI for Darwin Core Alignment
AI tools to aid in the transformation of "raw" biological occurrence data produced by researchers into standardized formats (Darwin Core (DwC)) for ingestion into systems like OBIS and GBIF.

Examples from the [Standardizing Marine Biological Data (SMBD) working group](https://github.com/ioos/bio_data_guide?tab=readme-ov-file#-how-to-participate) and associated annual Biodata Mobilization Workshops are available for use to guide AI prompt tailoring.

A successful project will likely include multiple AI prompts working through processes like:

* AI prompt generation and AI service API usage
* exposing a variety of "raw" data to an AI agent 
* using AI to map between "raw" and standardized vocabularies like DwC and NERC
* generating requests for additional information from data providers
* adding information received from data providers into standardized documentation
* generating standard documents for example datasets

Automation of the process through the GitHub issue tracker may be possible.
Use of automated emailing systems may be helpful as well.


#### Browser-based Darwin Core compliance checker

The IOOS Marine Life Data Network recommends aligning data that observes a species at a location and time to the DarwinCore Standard. Currently, there are various tools and resources available to check if a package matches the DarwinCore standard:

* <https://www.gbif.org/tools/data-validator>
* <https://github.com/iobis/obistools>
* <https://github.com/cioos-siooc/pyobistools>
* <https://gbif.es/en/software/darwin-test/>

Most of these checkers have some prerequisite requirements of installing additional software or creating an account in a system. Something that could be useful to the IOOS DMAC community would be an online web checker for DarwinCore, similar to the IOOS Compliance Checker - <https://compliance.ioos.us/index.html>, that doesn't require a log in and checks for additional aquatic characteristics in a dataset.

The idea is that this could be a relatively simple checker for the community to use to ensure their workflows are aligning with the standard.

An online checker that allows a user to:
* Upload a data file ([occurrence](https://rs.gbif.org/core/dwc_occurrence_2022-02-02.xml), [extended measurementorfact](https://rs.gbif.org/extension/obis/extended_measurement_or_fact_2023-08-28.xml), [event](https://rs.gbif.org/core/dwc_event_2022-02-02.xml), [DNA derived data](https://rs.gbif.org/extension/gbif/1.0/dna_derived_data_2024-07-11.xml) or other applicable [extensions](https://rs.gbif.org/extensions.html).) or a [DarwinCoreArchive](https://ipt.gbif.org/manual/en/ipt/latest/dwca-guide) package
* Checks for compliance with the DarwinCore standard. If DarwinCore Archive, checks compliance with that standard.
  * Adds additional checks for aquatic data (eg. on land? contains depth information? taxonomy aligns to [WoRMS](https://www.marinespecies.org/)?)
  * If metadata ([EML](https://eml.ecoinformatics.org/)) is provided, checks against that standard.
* Provides the response back as various outputs (pdf, html, json, etc.), 
* Provides a web enabled API, similar to the [compliance-checker API](https://github.com/ioos/compliance-checker-web/wiki/API)
* A compliant data file could be directly loaded to an IPT by an OBIS Node manager.


### Skills desired

Taxonomic Occurrence Data familiarity. Coding experience. API usage familiarity. Email or GitHub issues automation.


### Expertise

Intermediate


### Topic Lead(s)

@7yl4r, @mathewbiddle


### Relevant links

Resources:
- https://www.gbif.org/darwin-core
- https://dwc.tdwg.org/terms/
- https://discourse.gbif.org/t/how-i-check-darwin-core-datasets/3833
- https://ipt.gbif.org/manual/en/ipt/latest/dwca-guide
- https://rs.gbif.org/extensions.html
- https://manual.obis.org/darwin_core.html


Tools:
- https://github.com/cioos-siooc/pyobistools
- https://github.com/iobis/obistools
- https://github.com/iobis/obis-qc
- https://gbif.es/en/software/darwin-test/
- https://www.gbif.org/tools/data-validator 
- https://www.datafix.com.au/darwin-core-checker/
- https://rshiny.lifewatch.be/BioCheck/
- https://github.com/EMODnet/EMODnetBiocheck


**Functioning Prototype**

TBD


**Workflow**

Tasks:

1. 

**Updates**


