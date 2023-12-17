---
layout: post
title:  "Testing the Li Keqiang Index: Analysis"
author: William
description: The results of my Li Keqiang Index project.
image: /assets/images/blog-image.jpg
---

# To Recap
[The previous blog post](https://wijama.org/2023/12/15/Li-Keqiang-Index-Introduction-and-EDA.html) introduced the project and performed an EDA which raised some important concerns. Because of our EDA, we chose to perform our analysis using the logged forms of our main variables of interest: GDP, rail cargo volume, and electricity consumption. (Bank loan volume had been omitted from the analysis because no reliable data exists.) We also noticed that there was autocorrelation within countries, which would have to be dealt with. Finally, we noticed problems with our data set in general, which will be discussed at the end of this analysis.

# Model Building
The goal of this analysis was to see if rail cargo volume and electricity consumption are good estimators of GDP. I also wanted to see if this would be impacted by economic variables such as the percentage of the population in urban areas and the percentage of the economy made up of the service sector. I also wanted to see if this would be impacted by the strength of democracy in the country of interest. I expected countries with lower levels of democracy to be more likely to overreport their GDP.
To this end, I built two models: one with just the variables of interest and one that included interactions between my control variables and the economic indicators. Using the statsmodels formula API, the first model is:
```
log_GDP ~ log_energy_cons+log_rail_cargo
```
And the second model is:
```
log_GDP ~ (log_energy_cons+log_rail_cargo)*(urban_per+service_per+democracy)-(urban_per+service_per+democracy)
```
`urban_per`, `service_per` and `democracy` are removed from the model because I am only interested in how they change the effect of the two economic indicators.
