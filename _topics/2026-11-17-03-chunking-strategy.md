---
number: 3
title: Optimize Chunking for Ocean model results
pis:
  - (@jonmjoyce)
  - (@ChrisBarker-NOAA)
contributors:
  - TBD
github: ioos/ioos-code-sprint/issues/84
slack:
  - TBD
breakout:
  - TBD
year: 
  - 2026
---

As things move forward with putting more model results in the cloud (e.g. the NODD), Zarr, Kerchunk, Icechunk etc can make them more accessible. (e.g. <https://github.com/ioos/ioos-code-sprint/issues/83> , <https://github.com/ioos/ioos-code-sprint/issues/80>).

However, that is accessing whatever chunks are available. This is all the more critical. as the entire chunk needs to move out of the cloud (if you're not running on the cloud) -- or from AWS storage to the VM running the code (in the cloud) either way, it can have large impacts on performance.

There is no one "optimum" chunking strategy, but the ones used by at least some of the NOS OFSs are pretty bad for any access pattern. For instance, most of the FVCOM models have the entire depth as one chunk -- if someone wants, say, surface currents, you're moving through a lot of data to get that small fraction.

Options are:

* Rechunk to "square" chunks that are as small as is practical.
  * that would result in non-optimum, but not horrible performance for any access pattern
  * NOTE: experiment with a local hard drive told me that tiny (<1k) chnnks are bad, and huge (> 10MB) chunks are bad, but anything it between was similar performance. That was with local disk and a long time ago, so those number aren't helpful, but the idea is ...
* Duplicate the files with different chunking, optimized for different use-cases.

e.g. TIme series at a point, vertical profile, horizontal region.
Of course, now that I write that, I think there's at least those three separate access patterns. (aarrgghh!)

**Advanced related topic:**
Unstructured grids are a challenge, because nodes that are close together in physical space may be far apart in index space -- so to get even a small region, you may need to grab many chunks in space.

One way to help this is to re-order the grids' node IDs -- putting physically close together nodes close together in index space. So grabbing a small region only requires a few chnuks.

Some work on this was done by the STOFS project, but I can't find it right now.

There is this that could be helpful:

<https://medium.com/pangeo/rechunker-the-missing-link-for-chunked-array-analytics-5b2359e9dc11>

**Expected Outcomes**

- 

**Skills required**

- 

**Expertise**

Novice

**Topic Lead(s)**

@jonmjoyce, @ChrisBarker-NOAA

**Relevant links**

* 

**Functioning Prototype**

TBD

**Workflow**

Tasks:

1. 

**Updates**


