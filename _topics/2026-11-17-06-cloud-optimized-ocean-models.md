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
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2026
---

**TL;DR**

This project merges IOOS Code Sprint topics #80 and #83. It focuses on utilizing agentic coding tools (e.g., Claude) to construct cloud-native workflows for ocean model output. Key deliverables include generating virtual Icechunk datasets, creating STAC catalogs stored in GeoParquet, and developing downstream applications and analytical workflows that query these records.

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

* A documented methodology for producing virtual Icechunk datasets from ocean model output.
* Example STAC catalogs hosted in GeoParquet format.
* Reference implementations of analytical workflows and prototype web applications driven by STAC queries.
* An assessment of agentic coding efficacy in constructing cloud-native Earth data architectures.

### Skills required

Ability to type some prompts!

### Expertise

Understanding what users might like.

### Topic Lead(s)

Eli Holmes, Rich Signell

### Relevant links

_No response_

**Functioning Prototype**

TBD

**Workflow**

Tasks:

1. 

**Updates**

