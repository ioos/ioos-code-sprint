---
number: 7
title: AI Ready Data Checker
pis:
  - Hassan Moustahfid (@hmoustahfid-NOAA)
contributors:
  - Megan Cromwell (@megancromwell)
github: ioos/ioos-code-sprint/issues/32
slack:
  - TBD
breakout:
  - unconference
year: 
  - 2024
---

The ESIP community developed a Checklist to examine AI-Readiness for open environmental datasets. 
Some early evaluation of this checklist shows that the checklist asks questions, but it doesn't score your answers, so it's up to the user to guess whether the checklist believes that all "no '''s are equally bad. 
It will be worth evaluating this checklist and developing a potential Checker for IOOS RAs to make sure we get our Datasets AI ready.
We started circulating a questionnaire to NOS offices and Programs and we are getting some interesting answers. To gather more information from RAs we will be circulating the same questionnaires.
Please take some time to consider the following questions for each of your program offices. This example of the ESIP community developed AI-readiness checklist may be beneficial in answering these questions.

Would you consider your program offices' open environmental data AI ready?
Are there particular aspects/parameters for your data that prevent it from being AI ready?
Have you/anyone in your program office used an AI-readiness checklist before?
For current projects leveraging AI, were there additional measures taken to get the data AI ready? What were they?

**Expected Outcomes:**

Prototype an AI Ready Data Checker/or assessment tool that can score each checklist question etc. Again we will be listening to y’all for other ideas.

**Skills required:**

- Data science
- Understanding AI ready Data (ESIP- <https://www.esipfed.org/merge/collaboration-updates/checklist-ai-ready-data>)
- Data management

**Difficulty:**

Intermediate

**Relevant links:**

ESIP AI Ready Data [Checklist ](https://www.esipfed.org/merge/collaboration-updates/checklist-ai-ready-data)

Here are some examples of existing compliance checkers/assessment tools to evaluate and learn from to develop AI Ready Data checkers or assessment tools to respond to the needs of the AI community. Please see above the concerns and challenges that folks are facing to evaluate if they are compliant with the ESIP AI Ready Data checklist.

| Examples  |Organization  | What's for?|
|--------|--------|--------|
|[IOOS Compliance Checker](https://compliance.ioos.us/index.html) | [NOAA IOOS](https://ioos.noaa.gov/) | The IOOS Compliance Checker is a Python-based tool for data providers to check for completeness and community standard compliance of local or remote netCDF files against CF and ACDD file standards. The Python module can be used as a command-line tool or as a library that can be integrated into other software.|
|[FAIR Data Assessment Tool-f-uji](http://www.f-uji.net/)| [PANGAEA](https://www.pangaea.de/) |F-UJI is a web service to programmatically assess FAIRness of research data objects at the dataset level based on the FAIRsFAIR Data Object Assessment Metrics|
|[pyQuARC](https://github.com/NASA-IMPACT/pyQuARC)|[NASA](https://www.nasa.gov/) | Open Source Library for Earth Observation Metadata Quality Assessment|
|[FAIR-Checker](https://fair-checker.france-bioinformatique.fr/) | [Looks like French Group](https://jbiomedsem.biomedcentral.com/articles/10.1186/s13326-023-00289-5)| Assess FAIRness|

- A capability maturity model for scientific data management - https://doi.org/10.1002/meet.14504701359
- A Unified Framework for Measuring Stewardship Practices Applied to Digital Environmental Datasets - https://datascience.codata.org/articles/10.2481/dsj.14-049

**Functioning Prototype**

None yet!

**Workflow**

Tasks:

1. Review the ESIP AI Ready Checklist (focus on Training Data level 3 Metadata?) 
1. Evaluate existing checker (differences) commonalities etc.  
1. Select a checker to build on/prototype etc. 
