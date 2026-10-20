---
number: 5
title: Work on Icechunk for ERDDAP (xpublish-erddap plugin, Zarr v3/Icechunk serving for ERDDAP)
pis:
  - @eeholmes
contributors:
  - 
github: ioos/ioos-code-sprint/issues/82
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2026
---

This project is around providing Icechunk support in ERDDAP. There are a few project:

- [ ] work on **https://github.com/xpublish-community/xpublish-erddap** a plug-in for xpublish to allow icechunks to be served as if they came from an ERDDAP server. Important for Icechunks served in Earthmover's Arraylake since it provides and ERDDAP-like end-point for users (who are already familiar with getting data from ERDDAP urls).
- [ ] work on [EDD*FromErddap for an ERDDAP server to proxy icechunk datasets](https://github.com/xpublish-community/xpublish-erddap/issues/53)
- [ ] Research what it would be involved in Icechunk support for ERDDAP. Closely related to PR #617 https://github.com/ERDDAP/erddap/pull/617 and probably depends on that. 
- [ ] Work on a Icechunk/Zarr validator for ERDDAP readiness since ERDDAP imposes rules on gridded data that not all (or not many) icechunks or Zarr stores will satisfy. Note ERDDAP probably already has this.

### xpublish-erddap

Here is a working prototype to build on: **https://github.com/xpublish-community/xpublish-erddap**. Note the prototype is largely done and the team would work on testing the plug-in. The second thing we could work on is sorting out what would be necessary for ERDDAP servers to be able to serve icechunks, esp as Earthmover/icechunk is in the works for hosting more NOAA data.

## Motivation

A lot of ocean and climate data is moving from file-based archives to cloud-native
Zarr — and increasingly to [Icechunk](https://icechunk.io) stores on platforms like
Earthmover's Arraylake. That migration is good for the people *producing* and
*analysing* data at scale, but it breaks people's existing code that accessed the data before migration.

Many of our users reach our data through the ERDDAP ecosystem: **[erddapy](https://ioos.github.io/erddapy/)**
in Python, **[rerddap](https://docs.ropensci.org/rerddap/)** in R, ERDDAP formatted urls, and a large body
of scripts, notebooks, teaching material and operational workflows built on top of
them. Those tools speak ERDDAP's REST API — `griddap` URLs with ERDDAP's own
subsetting syntax, plus its `info` and `search` endpoints. They cannot talk to a
Zarr store or an Icechunk repository.

As we move data into cloud-native formats, Zarr/Icechunk, we break our users data analysis pipelines. 

**The idea:** put an ERDDAP-compatible API in front of generic xarray-readable data,
so that a Zarr or Icechunk dataset can be reached with the ERDDAP tooling people
already use. If we get this right, migrating a dataset off an ERDDAP server becomes
invisible to the people using it — their existing `erddapy` and `rerddap` (etc) code keeps
working, unchanged.

This is deliberately **not** about recreating ERDDAP. We want the API surface those client
libraries actually call. The UI machinery: Data Access Form, "Make A Graph", or the admin machinery could be a different project if that were needed.

### Why this is tractable

[Xpublish](https://github.com/xpublish-community/xpublish) is a pluggable server that
publishes xarray datasets over HTTP, and the community already has plugins for
OPeNDAP, WMS, EDR and Zarr — but **nothing for ERDDAP**. Xpublish is also what
Earthmover's Flux uses to serve DAP2 from Icechunk, so the pattern is proven at
scale.

Here is a working prototype to build on: **https://github.com/eeholmes/xpublish-erddap**.
It already serves `griddap` with ERDDAP's coordinate-value subsetting, and both
`erddapy` and `rerddap` run against it unmodified — verified against real NOAA CEFI
model output read from Icechunk. It is a prototype, not a product: no auth, no
tabledap (which might be out of scope anyhow), a partial file-type list, and a backlog of
[open issues](https://github.com/eeholmes/xpublish-erddap/issues).

Building it surfaced the thing that makes this more interesting than "implement a
documented REST API": **the client libraries are coupled to ERDDAP's exact
formatting, not just its URL scheme.** For example, `erddapy` parses the DDS with
`data.split("GRID")`, so the keyword must be uppercase even though the DAP2 spec
says otherwise; `rerddap` asserts on an exact `content-type` string; and it reads
`time_coverage_start`/`_end` *positionally*, which only works because ERDDAP emits
global attributes alphabetically. Each of those was found by a client crashing.
There are almost certainly more.

## Expected Outcomes

###  `xpublish-erddap` — the server plugin

- Harden the prototype: authentication, better error messages, more of ERDDAP's
  output file types (`.nccsv`, `.htmlTable`, `.parquet`)
- **Validate against a real ERDDAP instance.** Everything so far is written against
  *client* behaviour, never against ERDDAP itself. Standing up a dockerised ERDDAP
  and diffing responses byte-for-byte would turn guesses into guarantees
- Broaden client coverage — more `erddapy`/`rerddap` versions, and other ERDDAP packages
- After getting it into reasonable shape: propose it to
  [xpublish-community](https://github.com/xpublish-community) alongside the existing
  plugins

## Skills required

Realistically, the biggest skill needed is being able to develop test cases and run tests for Claude Code. The next biggest skill would be familiarity with ERDDAP. Being able to find code examples that we can test would be good.

For coding: Python, xarray. Useful but not required: FastAPI, Zarr/Icechunk, R, 
familiarity with ERDDAP or CF/ACDD metadata conventions. 

## Expertise

Beginner to Intermediate

## Topic Lead(s)

Eli Holmes (@eeholmes), Alex Kerney (maybe, he inspired the idea and suggested the prototype)

## Relevant links

- Prototype: https://github.com/eeholmes/xpublish-erddap
- Open issues / backlog: https://github.com/eeholmes/xpublish-erddap/issues
- Xpublish: https://github.com/xpublish-community/xpublish
- Existing plugins for comparison: [xpublish-opendap](https://github.com/xpublish-community/xpublish-opendap), [xpublish-edr](https://github.com/xpublish-community/xpublish-edr), [xpublish-wms](https://github.com/xpublish-community/xpublish-wms)
- erddapy: https://ioos.github.io/erddapy/
- rerddap: https://docs.ropensci.org/rerddap/
- ERDDAP griddap documentation: https://coastwatch.pfeg.noaa.gov/erddap/griddap/documentation.html
- Icechunk: https://icechunk.io
- Earthmover Flux (Icechunk served over DAP2/WMS/EDR): https://www.earthmover.io/blog/announcing-flux/

**Functioning Prototype**

TBD

**Workflow**

Tasks:

1. 

**Updates**


