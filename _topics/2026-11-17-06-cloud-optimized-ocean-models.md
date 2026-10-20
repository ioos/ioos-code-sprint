---
number: 6
title: Create cloud-optimized virtual ocean-model datasets and services
pis:
  - @eeholmes
contributors:
  - TBD
github: ioos/ioos-code-sprint/issues/83
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2026
---

Let's use agentic coding (e.g. Claude, Antigravity, CODEX) to create new cloud-optimized data stores and services that are built off icechunks. Goal is to increase the world of cloud-optimized and accessible ocean model data and services that build off them. Things you might work on in this team

* build new virtual and native Icechunks on object storage (you can add to our Source Coop org which already has icechunks)
* develop xpublish-based services (OPeNDAP, WMS, OGC Tiles)
* create user-facing web apps that consume data directly from icechunk, OGC services and ERDDAP, like GridLook and ilk
* work on our icechunk/VirtualiZarr agent skill

**Expected Outcomes**

Increased understanding of agentic coding and icechunks. New  notebooks and user-facing web apps that demonstrate the power, performance of this approach. Reproducible ingestion and validation notebooks. Recommendations for publishing cloud-optimized ocean-model NetCDF files.

### Some examples of specific tasks you might take on

**on a Icechunk building project**

* Identify suitable ocean-model archives and assess their formats, chunking, and access constraints.
* Virtualize well-chunked NetCDF files without copying the source data.
* Test common workflows such as maps, regional subsets, profiles, and point time series.
* Measure data transfer and read amplification.
* Document when source files must be spatially or temporally rechunked before virtualization.

**on a visualization project**

* Use an agent to understand a current dashboard and how zarrita, icechunk-js and WebGL work together
* Brain storm what it would take to create 'preview' functionality that could be integrated into websites
* Build it with with an agent

**on an agent skills project**

* Talk with the other teams re what they are learning
* Point the agent to their repos, notebooks and scripts and guide the agent to learn the gotchas
* Talk with icechunk experts and gather more info on what is critical in an icechunk skill
* Build it with an agent!

### Why cloud-optimized, Why VirtualiZarr and Icechunk?

Ocean model output especially is so so many netcdf files. Sadly much is unsuitable for virtualization (it is unchunked and files are one single massive chunk), but lots is suitable and we have tricks for dealing with some unchunked types. But we need more icechunks built with different types of source files so that we can learn.

<img width="722" height="389" alt="Image" src="https://github.com/user-attachments/assets/6c032205-0885-44ad-9700-b5f3bfff3e28" />

<img width="724" height="412" alt="Image" src="https://github.com/user-attachments/assets/d014622f-827c-4185-8c75-209b69a61efd" />


### Expected Outcomes

_No response_

### Skills required

_No response_

### Expertise

None

### Topic Lead(s)

_No response_

### Relevant links

_No response_

**Functioning Prototype**

TBD

**Workflow**

Tasks:

1. 

**Updates**


