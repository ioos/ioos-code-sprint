---
number: 5
title: Exploring modern RESTful services for gridded data
pis:
  - Jonathan Joyce
contributors:
  - James Munroe
  - Alex Kerney
  - Max Grover
  - Matt Iannucci
github: ioos/ioos-code-sprint/issues/11
slack:
  - cloud
breakout:
  - Cloud/IoT
---

This project will explore passing gridded geospatial data through microservices. We would like to develop some standard HTTP interfaces for data requests and responses. The guiding principles for this work should focus on performance, accessibility, and interoperability.

We should at a minimum explore the following use cases:

1. Requesting many tiles of data, as one would against a WMTS
2. Requesting a time-series of data for a particular location
3. Requesting an entire grid of data

For the purposes of this project, we can assume the data sources will be in cloud-optimized formats such as Zarr, and we can use Xarray to efficiently access the data.
One possibility is that we extend the Xpublish library to support more data requests. ”Xpublish lets you easily publish Xarray Datasets via a REST API.”
We can evaluate OpenDAP as a possible protocol as long as it is performant and easy for clients to use.
Apache Arrow is another interesting library to explore, but its support for 2D data is limited so far. It limits the need for serialization and deserialization by manipulating data in-memory rather than passing it throughout the system.

**Expected Outcomes:**

Ideally this project will develop an API framework that can continue to be extended. This API should be easy to use and accessible from any standard programming language and not require managed dependencies.

Although having a fully-functional API is far-fetched from just this code sprint, we will hopefully discuss, identify, and resolve the sticking points around access to scientific gridded data.

**Skills required:**

Python, understanding of gridded data, REST APIs, willingness to think outside the box

**Difficulty:**

Moderate-Difficult

**Relevant links:**

* Project [page](https://asascience.github.io/restful-grids/project-overview.html) created during the sprint
* [https://docs.xarray.dev/en/stable/](https://docs.xarray.dev/en/stable/)
* [https://xpublish.readthedocs.io/en/latest/](https://xpublish.readthedocs.io/en/latest/)
* [https://arrow.apache.org/](https://arrow.apache.org/)
