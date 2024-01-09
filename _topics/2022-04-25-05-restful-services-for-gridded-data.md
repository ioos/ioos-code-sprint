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
year: 
  - 2022
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

---
# Updates from the Code Sprint Progress
Our primary repository can be found [in the restful-grids repo](https://github.com/asascience/restful-grids)

## Resources
Use this S3 bucket for test data: `s3://ioos-code-sprint-2022`
Several zarr datasets have been added to it. It also contains a static STAC catalog for identifying the data.

## Setup
[Miniconda](https://docs.conda.io/en/latest/miniconda.html) is recommended to manage Python dependencies.  

In the Anaconda prompt, you can load the `environment.yml` file to configure your environment:
`conda env create -f environment.yml`

Once you install the environment, you will need to activate it using

`conda activate code-sprint-2022`

To update your conda environment with any new packages added or removed to the `environment.yml` file use

`conda env update -f environment.yml --prune`

Alternatively, you can install dependencies with `pip` and `virtualenv`: 

```bash
virutalenv env/
source env/bin/activate
pip install -r requirements.txt
```

## Running This Work-In-Progress

Once you install your environment, you can run your local server with the:
- Wave Watch 3 (ww3) dataset, which can be downloaded [here]()
- Global Forecast System (GFS) in Zarr format hosted on the cloud

Once you have your data, use following steps:

### Start the Server
You can start the server using the `main.py` in the `/xpublish` directory

**Relevant links:**

* Project [page](https://asascience.github.io/restful-grids/project-overview.html) created during the sprint
* [https://docs.xarray.dev/en/stable/](https://docs.xarray.dev/en/stable/)
* [https://xpublish.readthedocs.io/en/latest/](https://xpublish.readthedocs.io/en/latest/)
* [https://arrow.apache.org/](https://arrow.apache.org/)
