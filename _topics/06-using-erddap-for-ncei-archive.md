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

**Code Sprint Activity**

After walking through using the `ArchiveADataset.sh` tool with Bob Simons, we identified the following process:
1. Create/edit a configuration file which lists the dataset ID's in the host ERDDAP to be archived at NCEI. This is a "Setting the 'ready for archival flag'".
   1. The data provider would have to manage which ones are new/updates. They can manage that by calculating the SHA-256 checksum of the jsonl response for the dataset of interest to see if the **data** changed.
1. Script (ran at some frequency TBD by provider) uses the config file to run `ArchiveADataset.sh` for each dataset.
   1. To run as a one liner with a Docker deployed ERDDAP, use this 
      ```
      $ docker run --rm -it \
      -v "$(pwd)/datasets:/datasets" \
      -v "$(pwd)/logs:/erddapData/logs" \
      -v "$(pwd)/erddap/content:/usr/local/tomcat/content/erddap" \
      -v "$(pwd)/erddap/data:/erddapData" \
      axiom/docker-erddap:latest \
      bash -c "cd webapps/erddap/WEB-INF/ && bash ArchiveADataset.sh -verbose BagIt tar.gz default raw_asset_inventory default "" "" .nc SHA-256"
      ```
1. Resultant BagIt package is put in the appropriate WAF for NCEI to pick up.

**Next Steps**
* Chris Turner to test/build process for ATN satellite telemetry data.
* Bob Simons to add functionality to include additional files in the BagIt package (auto add ISO metadata record).
  * See: https://github.com/BobSimons/erddap/issues/45
* Matt Biddle to engage with other stakeholders for requirements (Nazila needs something specific for NMFS).

