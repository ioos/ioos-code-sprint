---
number: 3
title: User documentation on "how to get started with your erddap server"
pis:
  - Joeseph Smith
contributors:
  - Mathew Biddle
  - Fernando Pacheco
github: ioos/ioos-code-sprint/issues/4
slack:
  - erddap
breakout:
  - ERDDAP
---

User documentation on how to get started with your erddap server.

**Expected Outcomes**

A more robust how-to guide for deploying, managing, and updating an erddap server. Could follow the IOOS Documentation website theme built out of the ioos/erddap-gold-standard repo.

Some bullet points to hit (please add more or contact joe@glos.org to do so):

- Local development (Windows, Mac, Linux, given who's available)
- On-premesis, or non-kubernetes cloud machine setup
  - How to use Docker for ERDDAP
- Kubernetes setup (for ERDDAP 2.18+; that had some breaking changes for particular setups)
- Working the `datasets.xml` file, quirks, what's worked in practice
  - Time series data
  - Spatial data
  - Bio data
  - Other
- Tools for easing data integration into ERDDAP

**Skills required**

* Markdown
* GH-pages??
* Docker, Kubernetes pod skill

**Difficulty:**

Moderate

**Relevant links:**

* [https://github.com/ioos/erddap-gold-standard/issues/8](https://github.com/ioos/erddap-gold-standard/issues/8)
* [https://github.com/ioos/erddap-gold-standard/issues/5](https://github.com/ioos/erddap-gold-standard/issues/5)

**Code Sprint Activity**

After developing a plan of action, there was a flurry of activity to establish concise instruction on setting up ERDDAP locally via a Docker container. Local development without Docker was dismissed due to being against the spirit of the exercise. Work was done to develop utility functions to interact with an ERDDAP container, and a guide to deploying on Kubernetes locally was developed.

[A website]() with this guide, has been developed. 

**Future work**

We will want to develop a guide on deploying ERDDAP via Docker or Kubernetes on a live server or cluster. Further development of the utility functions and using the flag system.
