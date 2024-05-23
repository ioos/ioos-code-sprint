---
number: 5
title: Collect data usage statistics from OBIS and GBIF and add to ioos_metrics
pis:
  - MathewBiddle
contributors:
  - laurabrenskelle
  - 7yl4r
github: ioos/ioos-code-sprint/issues/55
slack:
  - python
breakout:
  - Unconference
year: 
  - 2024
---
IOOS would like to be able collect metrics about how data are being used and downloaded from the OBIS and GBIF repositories. 
These metrics highlight the impact of IOOS data beyond its initial collection purpose. 
The function should be added to the existing ioos_metrics library. <https://github.com/ioos/ioos_metrics>

**Expected Outcomes:**

* run a function that collects metrics from OBIS and GBIF.
* summarizes information into a CSV file for reference in reports/webpages.
* optional create metrics webpage on <https://ioos.github.io/ioos_metrics/>

**Skills required:**

* Experience with Python
* Experience with OBIS/GBIF API.

**Difficulty:**

Novice

**Relevant links:**
- <https://github.com/ioos/ioos_metrics/issues/69>
- <https://github.com/ioos/mbon-docs/issues/45>
- Pull Request - <https://github.com/ioos/ioos_metrics/pull/74>

**Functioning Prototype**
* <https://github.com/MathewBiddle/sandbox/blob/main/notebooks/MBON_OBIS_statistics.ipynb>

**Workflow**
* add function to `ioos_metrics`
* parse results in jupyter notebook added to `ioos_metrics/notebooks` and visualize something important.

```python
import ioos_metrics.ioos_metrics

df = ioos_metrics.ioos_metrics.mbon_stats()
```

**Notebook**
<https://github.com/ioos/ioos_metrics/blob/main/notebooks/mbon_citation_visualizations.ipynb>

**Images**

![](image.png)
![](image_copy.png)
![](image copy 2.png)
![](image copy 3.png)
![](image copy 4.png)
![](newplot.png)
