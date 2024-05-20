---
number: 3
title: ERDDAP web logs analysis
pis:
  - Callum Rollo
contributors:
  - tbd
github: ioos/ioos-code-sprint/issues/34
slack:
  - python
breakout:
  - General Python
year: 
  - 2024
---

Develop a tool that reads in the web logs of an ERDDAP server to analyse how the server is being used. This would include:

- Filtering out bots/crawlers/spam
- Analysing and visualising which datasets receive the most requests
- Examining geographical/temporal distribution of users
- Investigating what user agents are making requests (browsers, erddapy, other ERDDAP servers etc.)

Initially this will be a static tool that is run on the tomcat/nginx logs of an ERDDAP server. The next step will be to run it alongside the ERDDAP server perhaps with a tool like prometheus

**Expected Outcomes:**

A python based tool that ERDDAP admins can use to quickly and easily establish how data from their server are being used.

This tool will be rapidly iterated on by the community (current ERDDAP operators). Once the tool is stable, it may be integrated into core ERDDAP, or changes made to core ERDDAP to enable the tool to be used more easily

**Skills required:**

- Python
- Some knowledge of servers/web logs useful
- Access to logs from an active ERDDAP server useful


**Difficulty:**

Novice

**Relevant links:**

Work in progress here https://github.com/callumrollo/erddaplogs

Other potentially relevant tools that have been referenced:
- https://github.com/axiom-data-science/erddap-metrics
- https://github.com/dfo-meds/erddaputil

**Functioning Prototype**

**Workflow**
