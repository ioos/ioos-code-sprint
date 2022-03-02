---
number: 3
title: Characterising the marine carbon cycle in CMIP6
pis:
  - Oliver Andrews (University of Bristol)
  - Jamie Wilson (University of Bristol)
contributors:
  - Alan Kennedy-Asser
  - Anna Katavouta
  - Ben Blackledge
  - Chelsey Baker
  - Emily Vosper
  - Francisco de Melo Virissimo
  - Fraser Goldsworth
  - Katie Sieradzan
  - Markus Adloff
  - Qian Liu
  - Ros Death
  - Rui Ying
github: cmip6moap/project03
video_time: 1051
video_thumbnail: project03
---

Recent ocean heat uptake has been unprecedented, with the last five years being
the warmest in recorded history. Superimposed on this secular trend,
human-induced warming of the oceans has also caused more persistent and intense
periods of extreme sea surface temperature, termed ‘marine heatwaves’. Marine
heatwaves can rapidly disrupt marine life and commercial fisheries as organisms
are exposed to extreme conditions outside of their normal ranges. Recent
high-profile marine heatwaves, most notably in the North Pacific, have triggered
mass die-offs and shifts in ecosystem structure. Alongside this, climate-driven
changes in marine biogeochemistry, particularly ocean deoxygenation and
acidification, are imposing additional stress on marine ecosystems. Just as for
heatwaves, more extreme shifts in biogeochemistry are an expected consequence of
climate change, and individual cases of extreme, inhospitable low-oxygen or
low-pH conditions are on the rise. However, the increased persistence of marine
biogeochemical extremes in a changing climate remains underexplored by the
scientific community, despite major consequences for ecosystem stability.

Plankton ecosystems continuously sequester ~1700 Pg of carbon from the
atmosphere in the deep ocean via sinking particles of organic matter. The
production of these particles is projected to decrease during the 21st century
in response to warming-driven stratification of the surface ocean (Bopp et
al., 2013). However, models are now including newly identified processes, such
as temperature-dependent degradation, that influence how far these particles
sink into the oldest deep ocean which in turns changes how long that carbon is
stored for. However, this is not consistent across models. The impact of these
new processes on future projections has yet to be quantified – do they change
future projections of biologically sequestered carbon? Does the varied
representation of sinking particles influence projections?

In this hackathon group we will use CMIP6 data (OMIP, DAMIP, scenarioMIP) to
assess historical and projected future changes in marine biogeochemistry from
timescales of daily extremes to long term (multidecadal) carbon storage.

Possible outcomes:
1. Marine extreme events atlas: Mapping present and future co-occurrence of
   marine heatwaves + biogeochemical extremes (and their physical drivers –
   including stratification, eddy influence, atmospheric heatwaves). Specific
   focus will be given to high SST, low chlorophyll extremes.
2. Future changes in biological carbon sequestration: Quantifying present and
   future carbon sequestration by marine biology across different models.
   Specific focus will be given to identifying the role of biological and
   physical drivers.

Possible methods: 
- (compound) extreme event statistics
- climate attribution
- analysis of physical drivers (eddy-tracking, Lagrangian framework)
- downscaling or bias adjustment
- analysis of biological drivers (export production, degradation of organic
  carbon)
- quantifying carbon storage using apparent oxygen utilisation

Possible CMIP6 outputs to target:
- experiments: piControl, historical, hist-NAT, hist-GHG, sspXXX
- ocean outputs: thetao, so, mlotstmax, moltsmin, uo, vo, ssh (Omon); tos,
  sos (Oday) 
- ocnBiogeochem outputs: o2, o2sat, ph, co3satarag, co3satcal, expc, epc100,
  intpp, diss14cabio, dissoc (Omon); chlos and phycos (Oday) 
