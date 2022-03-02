---
number: 10
title: Human heat stress in a warming world
pis:
  - Chris Smith (Leeds)
contributors:
  - Charles H. Simpson
  - Chloe Brimicombe
  - Claudia Di Napoli
  - Gibran Hemani
  - Laila Gohar
  - Lauren Burton
  - Michael Taylor
  - Rachel Tunnicliffe
  - Robin Lamboll
  - Seb Cole
github: cmip6moap/project10
video_time: 2587
video_thumbnail: project10
---

Climate projections tend to agree that extremes of heat over the populated land
surface areas of the world will rise faster than the global mean surface
temperature (Samset et al., 2018; Schleussner et al., 2016; Seneviratne and
Hauser, 2020). Traditional extremes of heat and other climate indices defined by
the ETCCDI such as monthly maximum temperature or heatwave duration (Zhang et
al., 2011) do not directly estimate the impacts on human welfare. In this work I
propose to directly compute a metric of human heat stress, the Universal Thermal
Climate Index (UTCI; Błazejczyk et al., 2013), using CMIP6 projections. This
work will build on the work of Claudia Di Napoli (U. Reading) who has used UTCI
in the present climate with reanalysis data (Di Napoli et al., 2020). Claudia or
others from Reading could be invited to collaborate on this project as part of
the MOAP group.

The work would proceed as follows:
1. Obtaining 3-hourly CMIP6 data from participating CMIP6 models. The
   following variables are required on 3-hour resolution: tas, hurs, rlds,
   rlus, rsus, rsds, plus one of rsdsdiff or rsdt, and ideally (vas and uas)
   or sfcWind
2. Bias-correction of this data to correct for any model biases in absolute
   temperatures in the present-day and recent past.
3. Calculation of UTCI from the bias-corrected data
4. Presenting the change in UTCI, and absolute projected UTCI, as spatial
   plots under different SSP scenarios at the end of the 21st Century
5. Determining the change in UTCI as a function of global mean surface
   temperature for each of the Giorgi world regions (Giorgi and Francisco,
   2000), allowing these projections to be scenario-independent and coupled to
   a simple emissions-based climate model (Smith et al., 2018).
6. Implementation of this into an interactive web tool showing regional heat
   stress as a function of global mean temperature change. Open-source tools
   for calculating UTCI from climate data are already available , and the hope
   is that this project will help develop this software repository further to
   be more useful to the research community.

References
- Błazejczyk, K., Jendritzky, G., Bröde, P., Fiala, D., Havenith, G., Epstein,
  Y., et al. (2013). An introduction to the Universal thermal climate index
  (UTCI). Geogr. Pol. 86, 5–10. <https://doi.org/10.7163/GPol.2013.1>
- Di Napoli, C., Hogan, R. J., and Pappenberger, F. (2020). Mean radiant
  temperature from global-scale numerical weather prediction models. Int. J.
  Biometeorol. 64, 1233–1245. <https://doi.org/10.1007/s00484-020-01900-5>
- Giorgi, F., and Francisco, R. (2000). Uncertainties in regional climate change
  prediction: A regional analysis of ensemble simulations with the HADCM2
  coupled AOGCM. Clim. Dyn. 16, 169–182. <https://doi.org/10.1007/PL00013733>
- Samset, B. H., Sand, M., Smith, C. J., Bauer, S. E., Forster, P. M.,
  Fuglestvedt, J. S., et al. (2018). Climate Impacts From a Removal of
  Anthropogenic Aerosol Emissions. Geophys. Res. Lett. 45, 1020–1029.
  <https://doi.org/10.1002/2017GL076079>
- Schleussner, C. F., Lissner, T. K., Fischer, E. M., Wohland, J., Perrette, M.,
  Golly, A., et al. (2016). Differential climate impacts for policy-relevant
  limits to global warming: The case of 1.5 °c and 2 °c. Earth Syst. Dyn. 7,
  327–351. <https://doi.org/10.5194/esd-7-327-2016>
- Seneviratne, S. I., and Hauser, M. (2020). Regional Climate Sensitivity of
  Climate Extremes in CMIP6 Versus CMIP5 Multimodel Ensembles. Earth’s Futur. 8,
  e2019EF001474. <https://doi.org/10.1029/2019EF001474>
- Smith, C. J., Forster, P. M., Allen, M., Leach, N., Millar, R. J., Passerello,
  G. A., et al. (2018). FAIR v1.3: a simple emissions-based impulse response and
  carbon cycle model. Geosci. Model Dev. 11, 2273–2297.
  <https://doi.org/10.5194/gmd-11-2273-2018>
- Zhang, X., Alexander, L., Hegerl, G. C., Jones, P., Tank, A. K., Peterson, T.
  C., et al. (2011). Indices for monitoring changes in extremes based on daily
  temperature and precipitation data. Wiley Interdiscip. Rev. Clim. Chang. 2,
  851–870. <https://doi.org/10.1002/wcc.147>
