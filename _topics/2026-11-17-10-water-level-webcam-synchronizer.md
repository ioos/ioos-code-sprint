---
number: 10
title: Better Integrate RA Data and CO-OPS Tools + ERDDAP updates
pis:
  - (@conlin-matt)
contributors:
  - Katie DeVore
  - Keeney
  - Chris John
github: ioos/ioos-code-sprint/issues/77
slack:
  - (@erddap-co-ops-tools)
breakout:
  - 1
year: 
  - 2026
---

Enhance existing CO-OPS software tools (inundation analysis and WebCOOS camera synchronizer) to integrate with RA data.

### Expected Outcomes

CO-OPS provides two tools (among others) that could be of use to IOOS RAs: The [NWLON_WebCOOS Synchronizer](https://github.com/NOAA-CO-OPS/NWLON_WebCOOS_Synchronizer) and the [Tidal Analysis Datums Calculator](https://github.com/NOAA-CO-OPS/CO-OPS-Tidal-Analysis-Datum-Calculator). This topic will involve taking these exising tools and extending/adding-on to them to better integrate with RA data, and will result in multiple tools that IOOS RAs can use with their low-cost water level (and potentially other) data.

### Skills required

Python, ERDDAP knowledge useful

### Expertise

Intermediate 

### Topic Lead(s)

@conlin-matt

### Relevant links

[NWLON_WebCOOS Synchronizer](https://github.com/NOAA-CO-OPS/NWLON_WebCOOS_Synchronizer)
[Tidal Analysis Datums Calculator](https://github.com/NOAA-CO-OPS/CO-OPS-Tidal-Analysis-Datum-Calculator)

**Functioning Prototype**

See the [GitHub repo](https://github.com/NOAA-CO-OPS/NWLON_WebCOOS_Synchronizer)

**Workflow**

Tasks:

1. Spend some time thinking about inconsistencies in dataset names, variable names, data access patterns, etc. accross RAs and how it could be improved. Pull from existing literature potentially on the IOOS Code Lab. Discuss how these can be handled.
2. Prototype some integration of RA data into the existing codes.
3. Do some coding!

**Updates**

As of the end of Day 1:
- **Everyone is up to speed**: Everyone installed and got the `NWLON_WebCOOS-Synchronizer` code running
- **Failing tests fixed**: A couple failing tests were fixed


As of the end of Day 2:<br>
1. Progress improving the `NWLON_WebCOOS_Synchronizer` tool:<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **You can make a movie with RA data!**: Completed initial integration of `erddapy` and UI modifications for RA datasets.<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **You can run the code more easily**: Added a command line interface.<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **You can do a spatial search**: Added methods to geo-aggregate and find all NWLONs near a camera (and vice-versa).<br>
&nbsp;&nbsp;&nbsp;&nbsp;- **You can run the code faster**: Added methods to parallelize image download.<br>
2. Progress on integrating fuzzy search logic into ERDDAP

As of the end of Day 3:<br>
1. Completed working integration of `erddapy` and UI modifications for RA datasets into the `NWLON_WebCOOS_Synchronizer`.
<img width="1069" height="948" alt="Screenshot 2026-11-19 132622" src="https://github.com/user-attachments/assets/3387ff01-6a91-4171-b9bb-9172e592e6df" />
<img width="874" height="203" alt="Screenshot 2026-11-19 132833" src="https://github.com/user-attachments/assets/6856defc-cb42-4675-8fce-501697fb82b8" />


2. Completed initial implementation of ERDDAP smart search logic
<img width="1611" height="1244" alt="image" src="https://github.com/user-attachments/assets/362f9dfe-c466-4093-926b-b5332e42ef85" />

3. Added map showing sensor locations
<video src="https://github.com/user-attachments/assets/47398764-79af-4f90-a02a-58bffa202d51" width="640" height="360" controls></video>





 





