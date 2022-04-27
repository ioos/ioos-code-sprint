---
number: 7
title: IOOS QC Implementation for non-programmers
pis:
  - Ge (Jeff) Pu
contributors:
  - Dylan Pugh
  - Shelby Brunner
  - Ben Adams
github: ioos/ioos-code-sprint/issues/13
slack:
  - python
breakout:
  - General Python
---

Building an interactive user interface/application based on I0OS QC functions in [https:/ioos.github.io/ioos_qc/](https:/ioos.github.io/ioos_qc/). QC is 
important, reducing the complexity of QC process can encourage adoption of IOOS QC by diverse users, and in turn 
standardized it across broad user groups. Current documentation and code have been developed for programmers and 
non-programmers may have a hard time using IOOS QC. A possible starting point for this project could be 
[https://github.com/gp86041/IOOS_waterlevel_QC_interactive](https://github.com/gp86041/IOOS_waterlevel_QC_interactive).

**Expected Outcomes:**

Building an interactive application for non-programmers to upload and QC their data using QDOT functions.2.
Produce detailed documentation of how to use the application:
How to import data?
How to use the application?
How to understand the QC flags and further processing?

**Skills required:**

Either one of these:

* Basic Python
* Interactive Python
* Application Design

**Difficulty:**

Can vary from easy to difficult depending on skills of group members.

**Relevant links:**

* [https:/ioos.github.io/ioos_qc/](https:/ioos.github.io/ioos_qc/)
* [https://github.com/gp86041/IOOS_waterlevel_QC_interactive](https://github.com/gp86041/IOOS_waterlevel_QC_interactive)

**Functioning Prototype Repo**

* [ioos-qc-front-end](https://github.com/Dylan-Pugh/ioos-qc-front-end)

**Workflow**

1. Import data that need QA/QC
2. Select variable to be QA/QC
3. Select QC checker type (i.e. gross range test)
4. Select test parameters using a slider or numeric input
5. Run QARTOD 
6. Plot results (TBA, would be nice to have)
7. Download post QA/QC data with flags

