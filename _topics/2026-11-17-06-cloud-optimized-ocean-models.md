---
number: 6
title: Cloud-Native Ocean Model Workflows via Agentic Coding
pis:
  - Eli Holmes (@eeholmes)
  - Rich Signell (@rsignell)
contributors:
  - John Maurer (@johnolulu), PacIOOS project
  - Shane St Savage (@srstsavage), PacIOOS, icechunker tool
  - Jan (Honza) Rychlý (@honzaflash), PacIOOS project, icechunker tool
  - Michael McDonald, HYCOM project
  - Charan (@charan0520), TX-LA project, designed updater tool
  - Cheryl Morse (@cheryldmorse), SSCOFS project
  - Micah Wengren (@mwengren), infrastructure
github:
  - ioos/ioos-code-sprint/issues/83
  - ioos/ioos-code-sprint/issues/80
  - ocean-icechunks
slack:
  - ocean-modeling
breakout:
  - TBD
year: 
  - 2026
---

**TL;DR**

This project merges IOOS Code Sprint topics #80 and #83. It focuses on utilizing agentic coding tools (e.g., Claude) to construct cloud-native workflows for ocean model output. Key deliverables include generating virtual Icechunk datasets, creating STAC catalogs stored in GeoParquet, and developing downstream applications and Jupyter notebooks that query these cloud-optimized datasets (icechunks).

[Dive in via our project website](https://ocean-icechunks.github.io/2026-ioos-hackathon/) or [play with some cloud-optimized datasets in Colab](https://ocean-icechunks.github.io/2026-ioos-hackathon/examples/)

### Background

This effort combines proposals for agentic coding application and cloud-optimized virtual ocean-model dataset development. Managing and distributing large-scale coastal and ocean model output presents structural challenges for the IOOS community. Cloud-native data architectures, particularly Zarr and Icechunk, paired with SpatioTemporal Asset Catalogs (STAC), provide an efficient mechanism for data access and discovery. This project evaluates the application of agentic coding assistants to accelerate the development of these data engineering workflows.

### Objectives

1. **Agentic Coding Integration**: Utilize AI coding agents (e.g., Claude) to script, debug, and implement the data pipeline.
2. **Virtual Icechunk Construction**: Employ tools such as VirtualiZarr to generate virtual Icechunk datasets from existing ocean model output (e.g., NetCDF), avoiding direct data duplication.
3. **STAC Catalog Generation & GeoParquet Storage**: Generate STAC items and collections for the virtual Icechunks. Transition STAC item storage to GeoParquet using rustac-py and pyarrow to enable performant querying of large asset collections.
4. **Workflow Development**: Develop reproducible analytical workflows (e.g., Python/Xarray/HoloViz notebooks) and prototype applications (e.g., TypeScript/React with Zarr-layers) that initiate data retrieval via STAC queries.

### Methodology

The workflow begins with existing model output on cloud storage. Assisted by agentic tools, participants will execute Python scripts to generate virtual Icechunk representations. STAC metadata will then be generated and embedded into GeoParquet schemas. The final phase involves constructing downstream applications to demonstrate STAC-driven data discovery, opening the Icechunk representations via Xarray for visualization and analysis.

### Why cloud-optimized, why VirtualiZarr and Icechunk?

Ocean model output especially is so so many netcdf files. Sadly much is unsuitable for virtualization (it is unchunked and files are one single massive chunk), but lots is suitable and we have tricks for dealing with some unchunked types. But we need more icechunks built with different types of source files so that we can learn.

<img width="722" height="389" alt="Image" src="https://github.com/user-attachments/assets/6c032205-0885-44ad-9700-b5f3bfff3e28" />

<img width="724" height="412" alt="Image" src="https://github.com/user-attachments/assets/d014622f-827c-4185-8c75-209b69a61efd" />

### Expected Outcomes

* New cloud-optimized icechunks. We have a [Source Coop organization](https://source.coop/ocean-icechunks) for hosting.
* New notebooks that show people how to do cool things with Icechunks. See our [examples](https://ocean-icechunks.github.io/2026-ioos-hackathon/examples/)
* Example STAC catalogs hosted in GeoParquet format.
* Reference implementations of analytical workflows and prototype web applications driven by STAC queries.

### Skills required

Ability to type some prompts!

### Expertise

Understanding what users might like.

### Topic Lead(s)

Eli Holmes, Rich Signell

### Relevant links

* [Our tutorials](https://ocean-icechunks.github.io/2026-ioos-hackathon/)
* [Source Coop Ocean Icechunks](https://source.coop/ocean-icechunks)
* Tom Nichols (EarthMover) [How to make ai ready archives](https://www.earthmover.io/blog/ai-ready-scientific-data-archives)
* [JupyterHub for the hackathon](https://workshop.nmfs-openscapes.2i2c.cloud)

### What are we making?

Tasks:

1. [x] Build virtual Icechunks from ocean model and gridded output with agent skills, and publish them in the [Ocean Icechunks organization on Source Coop](https://source.coop/ocean-icechunks)
2. [x] Get participants set up on the [ocean-icechunks GitHub organization](https://github.com/ocean-icechunks), so they can contribute the scripts they use to construct their virtual Icechunks
3. [x] Set up those repos to keep the forecast model run collections on Source Coop up to date, by appending new runs to their virtual Icechunks


### New Icechunk Datasets

All of these are in the [Ocean Icechunks organization on Source Coop](https://source.coop/ocean-icechunks).

**HYCOM**
The Hybrid Coordinate Ocean Model (HYCOM) is an open-source data-assimilative computer model used to simulate and predict ocean circulation, temperature, salinity, and water velocity. These are Icechunks from the data on AWS Open Data: the GOFS 3.1 global reanalysis, with a Gulf of Mexico 1/100° reanalysis started during the Sprint (see Progress below).
https://source.coop/ocean-icechunks/hycom

**NOAA ECCOFS**
The East Coast Community Ocean Forecast System (ECCOFS) is a data assimilating ocean analysis and forecast system being developed by Rutgers University, the University of California Santa Cruz, Fathom Science Inc., and the National Ocean Service (NOS) of NOAA for transition to operations at NCEP in 2028. The ECCOFS domain spans the eastern seaboard of North America and Intra-Americas Seas from the Grand Banks of Newfoundland in the north to the mouth of the Orinoco River, Venezuela, in the south. ECCOFS will complement the existing WCOFS (West Coast Operational Forecast System) to achieve complete forecast coverage of U.S. territorial seas adjacent to the 48 contiguous states and Puerto Rico. Each day ECCOFS generates an ocean analysis using the Regional Ocean Modeling System (ROMS) 4-Dimensional Variational (4D-Var) data assimilation (DA) system constrained by ocean observations. The forecast resolution is 3 km in the horizontal at 50 vertical terrain-following levels.
https://source.coop/ocean-icechunks/noaa-eccofs

**SSCOFS**
The Salish Sea and Columbia River Operational Forecast System (SSCOFS) is a NOAA NOS operational forecast system for the Salish Sea and the Columbia River estuary, built on the unstructured-grid FVCOM model. These are virtual Icechunks of a best time series made from the forecast files on NOAA Open Data (`noaa-nos-ofs-pds`), with UGRID topology metadata so tools like Gridlook can draw the mesh.
https://source.coop/ocean-icechunks/sscofs


**PacIOOS**
Regional models of the ocean (ROMS), weather (WRF) and waves (WaveWatch III) for the main Hawaiian Islands, run by the Pacific Islands Ocean Observing System (PacIOOS) to simulate and forecast currents, temperature, salinity, winds and waves.
https://source.coop/ocean-icechunks/pacioos


### Progress

#### Infrastructure for creating cloud-optimized datasets

**Development Environment**

To support future Icechunking work that started during the Sprint, the NOS Coastal Sandbox Nebari deployment was updated to include the following packages:

* pixi: dependency management and alternative to conda environments
* claude CLI: for following the tutorial presented by Eli Holmes: https://ocean-icechunks.github.io/2026-ioos-hackathon
* gh CLI: for ease-of-use interacting with GitHub (and connecting with Claude or your coding harness of choice)

New accounts were created for Code Sprint participants without @noaa.gov email addresses to allow access to a shared environment for co-development.

**Future NODD Ocean Icechunk bucket**

Additionally, as a potential NOAA-hosted home for future ocean Icechunk aggregations, we discussed with NODD the potential for a dedicated “NOAA Cloud Optimized MetOcean Model Aggregations” bucket.  Stay tuned for more to come on that story!


#### HYCOM Gulf of Mexico icechunks

Work started on an Icechunk for the HYCOM-TSIS reanalysis, the 1/100° hourly Gulf of Mexico reanalysis (2001–2024; about 348,000 NetCDF files, 466 TB, on S3). During the Sprint we:

* We (HYCOM team + Eli) completed an audit of the GOM files on S3. This revealed a number of data issues, most importantly a change in the chunk layout after April 2024, so they cannot share one Icechunk array with the earlier files. Found source-file issues worth knowing if you read the files directly (land values do not match `_FillValue`, so land is not masked; the 3D longitudes drift slightly from 2021 on) and sent them, with the questions on the second chunk layout, to the HYCOM team. The full report was shared with the HYCOM data team for review.
* During the hackathon, we built and published a 2022 test store on Source Coop, with a [Gridlook viewer](https://data.source.coop/ocean-icechunks/test-repo/hycom/viewer/index.html#icechunk+https://data.source.coop/ocean-icechunks/test-repo/hycom/hycom-tsis-gom-reanalysis/hourly::varname=water_temp::dimIndices_MT=0::dimIndices_Depth=0) and [loading code](https://data.source.coop/ocean-icechunks/test-repo/hycom/README.md). It opens anonymously in about 1 s.
* Chose the 3D chunking by measuring a year of reads: with one depth level per chunk, a one-year hourly point time series takes 17 s, against 117 s with ten levels per chunk.
* We found and fixed memory growth in the build (flat at 2.7 GB for a year, from 6.0 GB). Updated the ocean-icechunks-skills with what we learned from this.
* Files are being added to the S3 bucket and there are gaps that will be filled in later. Thus we developed and tested  scripts to fill gaps after the store is built.

After discussion with the HYCOM team, settled on a plan of two stores: GOMb0.01 (to September 2024) and GOMe0.01 (experiment 028, still running) because they are viewed as 2 different products. The full build waits on the S3 copy and HYCOM's answers. Details: [ocean-icechunks/hycom](https://github.com/ocean-icechunks/hycom) and [hackathon issue #22](https://github.com/ocean-icechunks/2026-ioos-hackathon/issues/22).


#### PacIOOS icechunks

Employing Eli Holmes’ agentic skills in the Ocean Icechunks skills repository on GitHub, namely archive-to-cloud and virtual-icechunk, PacIOOS now has 4 datasets hosted in the cloud on Source Cooperative as Icechunks from NetCDF files that were originally stored on our local server. This includes regional forecast models of the ocean (ROMS), weather (WRF), and waves (WaveWatch III) for the main Hawaiian Islands, comprised of 13,317 NetCDF files and totaling 3.4 TB. The Source Coop pages also provide a link to the Gridlook WebGL-based viewer for generating online maps of each dataset. Eli got 3 of the 4 datasets onto Source Coop prior to the Code Sprint, and John Maurer worked through issues she identified in the WRF dataset during the Code Sprint to get that one onto Source Coop as well; details in issue #12. John also explored connecting these datasets into Earthmover but hit a few snags that need addressing before this can be completed; details in issue #31.

We added a GitHub action to build a tarball of the deployable icechunker tool payload and attach it as an artifact to a pre-release (basically a workaround to allow our artifact that gets built on every push to main to not expire).

https://github.com/ocean-icechunks/pacioos/releases/tag/icechunker-main

The tarball can be downloaded and extracted on the server, bootstrapped with the included bootstrap.sh script, lightly configured (mostly source-coop api key and email notification settings), and then scheduled in cron to run regularly and keep source.coop netcdf and icechunk datasets up to date according to the output of icechunker cron. User can also do dry run syncs, verify the health of the entire icechunk repo, clean up local temp and cache files, view installed toolset status, and check the health of the local icechunker install.

Shane St Savage and Honza Rychly worked on this component, with heavy use of
[ocean-icechunk-skills](https://github.com/ocean-icechunks/ocean-icechunks-skills).


#### SSCOFS icechunks

Cheryl Morse (RPS) built virtual Icechunks for SSCOFS during the Sprint ([ocean-icechunks/sscofs](https://github.com/ocean-icechunks/sscofs)):

* Built a best time series store from the SSCOFS forecast files on NOAA Open Data: for each valid time, the file from the most recent model run. The data stay in NOAA's bucket; the store holds only references.
* Added UGRID topology metadata (with `xarray-subset-grid`), so the unstructured FVCOM mesh can be subset by bounding box in Python and drawn in Gridlook (see the SSCOFS salinity screenshot below).
* Made a second, virtual-subchunks version that splits each source chunk into one time step and one vertical layer per chunk, without copying any data, so one layer at one time can be read without fetching the whole source chunk.
* Added GitHub Actions workflows that copy the stores to Source Coop, and a nightly check that the repo can sign in to Source Coop, the first step toward updating the store automatically. Both stores are now at [source.coop/ocean-icechunks/sscofs](https://source.coop/ocean-icechunks/sscofs).


#### Visualizations

Gridlook draws a virtual Icechunk straight from Source Coop in the browser, which makes it a quick way to check a new model aggregation. Rich Signell's [fork of Gridlook](https://rsignell.github.io/gridlook/) adds CF-compliant discovery of the lon/lat coordinates. The PacIOOS and HYCOM stores also link to their own Gridlook viewers from their Source Coop pages. Three examples from the Sprint:

**ECCOFS potential temperature.** The forward-run best time series on Source Coop (`noaa-eccofs/eccofs-avg-best`).

![ECCOFS potential temperature shown in gridlook](/ioos-code-sprint/assets/eccofs-gridlook.png)

**SSCOFS salinity.** The UGRID-compliant virtual Icechunk built by Cheryl Morse, drawn on its unstructured mesh.

![SSCOFS salinity shown in gridlook](/ioos-code-sprint/assets/sscofs-gridlook.png)

**TX-LA ROMS salinity forecast.** The virtual Icechunk built by Charan, which holds forecast runs indexed by forecast reference time.

![TX-LA ROMS salinity forecast shown in gridlook](/ioos-code-sprint/assets/txla-roms-gridlook.png)


#### Continuous updates tooling

For the PacIOOS project, a deployable toolkit (icechunker) was developed to deploy to a server
to facilitate continuous scheduled upload of NetCDF model data to source.coop and updating
of the corresponding icechunk datasets, also on source.coop. The deployed tool is self contained,
requires minimal configuration, and can be scheduled to run periodically via cron to sync and process
data, verify health of the entire icechunk dataset, and perform periodic clean up tasks.
Errors are reported to a configured user via email. See the PacIOOS update for details.

#### ocean-icechunks-skills

The [ocean-icechunks-skills](https://github.com/ocean-icechunks/ocean-icechunks-skills) repository holds the agent skills the teams used to build their Icechunks. During the Sprint:

* **Two new skills (Experimental), by Rich Signell:**
  * `building-fmrc-virtual-icechunk`: build and update a forecast model run collection (FMRC) as a virtual Icechunk, one forecast run appended at a time, with best-estimate reads using Rolodex. Tested on NOAA's GoMOFS bucket ([PR #17](https://github.com/ocean-icechunks/ocean-icechunks-skills/pull/17)).
  * `adding-ugrid-conventions`: add UGRID mesh metadata to unstructured-grid model output (FVCOM, SHYFEM, SCHISM, ADCIRC, with notes on ICON), including in virtual stores, so tools like Gridlook and xugrid can read the mesh ([PR #18](https://github.com/ocean-icechunks/ocean-icechunks-skills/pull/18)).
* **`virtual-icechunk` updated with lessons from the HYCOM Gulf of Mexico build, by Eli Holmes** ([PR #25](https://github.com/ocean-icechunks/ocean-icechunks-skills/pull/25)): keeping memory flat in long builds, scanning many HDF5 headers in processes rather than threads, checking `_FillValue` against the values actually written on land, checking every file rather than a sample, and splitting uncompressed source chunks into smaller virtual chunks, with the measured read times.
* **Issues opened by Eli Holmes from what the teams ran into**, for the next round of updates:
  * `archive-to-cloud`: how to resume interrupted uploads to Source Coop without overwriting files ([#15](https://github.com/ocean-icechunks/ocean-icechunks-skills/issues/15), from the PacIOOS upload script).
  * `virtual-icechunk`: publish each store's environment file, notebooks and build code beside it, with one viewer per product ([#19](https://github.com/ocean-icechunks/ocean-icechunks-skills/issues/19), from the PacIOOS stores).
  * A standard README template for every Source Coop product and Icechunk store ([#21](https://github.com/ocean-icechunks/ocean-icechunks-skills/issues/21)).
  * Whether to reference source files as `s3://` or `https://` ([#27](https://github.com/ocean-icechunks/ocean-icechunks-skills/issues/27)). Testing this is what found the performance issue below.


#### Icechunk performance issue: `s3://` references on HTTP/2 object stores

We found an Icechunk performance issue that makes virtual datasets 2–7× slower to read when their source files are referenced as `s3://` on object stores that offer HTTP/2, including Source Cooperative, GCS (through its S3 interface) and OSN. `https://` references to the same files are unaffected, as are AWS S3, Tigris, Wasabi and CloudFerro. It came up when we tested whether switching our source-file references from `https://` to `s3://` would matter: [earth-mover/icechunk#2571](https://github.com/earth-mover/icechunk/issues/2571)
