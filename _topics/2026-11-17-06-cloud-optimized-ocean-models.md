---
number: 6
title: Cloud-Native Ocean Model Workflows via Agentic Coding
pis:
  - (@eeholmes)
  - (@rsignell)
contributors:
  - TBD
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
2. [ ] Get participants set up on the [ocean-icechunks GitHub organization](https://github.com/ocean-icechunks), so they can contribute the scripts they use to construct their virtual Icechunks
3. [ ] Set up those repos to keep the forecast model run collections on Source Coop up to date, by appending new runs to their virtual Icechunks


### New Icechunk Datasets

**HYCOM**
The Hybrid Coordinate Ocean Model (HYCOM) is an open-source data-assimilative computer model used to simulate and predict ocean circulation, temperature, salinity, and water velocity. These are Icechunks from the data on AWS Open Data.
https://source.coop/ocean-icechunks/hycom

**NOAA ECCOFS**
The East Coast Community Ocean Forecast System (ECCOFS) is a data assimilating ocean analysis and forecast system being developed by Rutgers University, the University of California Santa Cruz, Fathom Science Inc., and the National Ocean Service (NOS) of NOAA for transition to operations at NCEP in 2028. The ECCOFS domain spans the eastern seaboard of North America and Intra-Americas Seas from the Grand Banks of Newfoundland in the north to the mouth of the Orinoco River, Venezuela, in the south. ECCOFS will complement the existing WCOFS (West Coast Operational Forecast System) to achieve complete forecast coverage of U.S. territorial seas adjacent to the 48 contiguous states and Puerto Rico. Each day ECCOFS generates an ocean analysis using the Regional Ocean Modeling System (ROMS) 4-Dimensional Variational (4D-Var) data assimilation (DA) system constrained by ocean observations. The forecast resolution is 3 km in the horizontal at 50 vertical terrain-following levels.
https://source.coop/ocean-icechunks/noaa-eccofs

**SSCOFS**


**PacIOOS**
Regional models of the ocean (ROMS), weather (WRF) and waves (WaveWatch III) for the main Hawaiian Islands, run by the Pacific Islands Ocean Observing System (PacIOOS) to simulate and forecast currents, temperature, salinity, winds and waves.
https://source.coop/ocean-icechunks/pacioos


### Progress

**Development Environment**
To support future Icechunking work that started during the Sprint, the NOS Coastal Sandbox Nebari deployment was updated to include the following packages:

* pixi: dependency management and alternative to conda environments
* claude CLI: for following the tutorial presented by Eli Holmes: https://ocean-icechunks.github.io/2026-ioos-hackathon
* gh CLI: for ease-of-use interacting with GitHub (and connecting with Claude or your coding harness of choice)

New accounts were created for Code Sprint participants without @noaa.gov email addresses to allow access to a shared environment for co-development.

**Future NODD Ocean Icechunk bucket**
Additionally, as a potential NOAA-hosted home for future ocean Icechunk aggregations, we discussed with NODD the potential for a dedicated “NOAA Cloud Optimized MetOcean Model Aggregations” bucket.  Stay tuned for more to come on that story!


**Visualizations**

Visualizations of the above Icechunks in Gridlook.  Gridlook (see this [forked copy](https://rsignell.github.io/gridlook/)) is an excellent tool for quick visualizations of model aggregations.  See some examples below:

![ECCOFS potential temperature shown in gridlook](/ioos-code-sprint/assets/eccofs-gridlook.png)

A [forked copy of gridlook](https://rsignell.github.io/gridlook/) (adds CF-compliant discovery of lon/lat coordinates) displaying a virtual Icechunk of ECCOFS forward run data stored on Source Coop (`noaa-eccofs/eccofs-avg-best` in the Ocean Icechunks organization).

![SSCOFS salinity shown in gridlook](/ioos-code-sprint/assets/sscofs-gridlook.png)

Gridlook exploring a UGRID-compliant virtual Icechunk for SSCOFS (Salish Sea and Columbia River Operational Forecast System), built by Cheryl Morse.

![TX-LA ROMS salinity forecast shown in gridlook](/ioos-code-sprint/assets/txla-roms-gridlook.png)

Gridlook view of the TX-LA ROMS virtual Icechunk on Source Coop, created by Charan. It holds forecast runs, indexed by forecast reference time.

***Tooling***

For the PacIOOS project, a deployable toolkit (icechunker) was developed to deploy to a server
to facilitate continuous scheduled upload of NetCDF model data to source.coop and updating
of the corresponding icechunk datasets, also on source.coop. The deployed tool is self contained,
requires minimal configuration, and can be scheduled to run periodically via cron to sync and process
data, verify health of the entire icechunk dataset, and perform periodic clean up tasks.
Errors are reported to a configured user via email. See below for more details.

### PacIOOS results ###

Employing Eli Holmes’ agentic skills in the Ocean Icechunks skills repository on GitHub, namely archive-to-cloud and virtual-icechunk, PacIOOS now has 4 datasets hosted in the cloud on Source Cooperative as Icechunks from NetCDF files that were originally stored on our local server. This includes regional forecast models of the ocean (ROMS), weather (WRF), and waves (WaveWatch III) for the main Hawaiian Islands, comprised of 13,317 NetCDF files and totaling 3.4 TB. The Source Coop pages also provide a link to the Gridlook WebGL-based viewer for generating online maps of each dataset. Eli got 3 of the 4 datasets onto Source Coop prior to the Code Sprint, and John Maurer worked through issues she identified in the WRF dataset during the Code Sprint to get that one onto Source Coop as well; details in issue #12. John also explored connecting these datasets into Earthmover but hit a few snags that need addressing before this can be completed; details in issue #31.

We added a GitHub action to build a tarball of the deployable icechunker tool payload and attach it as an artifact to a pre-release (basically a workaround to allow our artifact that gets built on every push to main to not expire).

https://github.com/ocean-icechunks/pacioos/releases/tag/icechunker-main

The tarball can be downloaded and extracted on the server, bootstrapped with the included bootstrap.sh script, lightly configured (mostly source-coop api key and email notification settings), and then scheduled in cron to run regularly and keep source.coop netcdf and icechunk datasets up to date according to the output of icechunker cron. User can also do dry run syncs, verify the health of the entire icechunk repo, clean up local temp and cache files, view installed toolset status, and check the health of the local icechunker install.

Shane St Savage and Honza Rychly worked on this component, with heavy use of
[ocean-icechunk-skills](https://github.com/ocean-icechunks/ocean-icechunks-skills).
