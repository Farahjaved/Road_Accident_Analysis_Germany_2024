nrw# Road_Accident_Analysis_Germany_2024
Analyzing road accident patterns in Germany in the year 2024, based on road surface, light conditions and driver behaviours.
# Project Overview
This repository contains a comprehensive Python-based analysis of Germany’s 2024 accident dataset, provided by OpenGEOdata.NRW. The project performs exploratory data analysis (EDA) and cluster segmentation to uncover meaningful accident patterns across municipalities.
The analysis focuses on three key dimensions that influence road safety:

+ Light conditions (daylight, darkness, twilight)

+ Road surface conditions (dry, wet, slippery)

+ Driver behaviors (error-related, turning, same-direction conflicts, etc.)

The objective is to identify high-risk accident environments and provide insights that help policymakers and urban planners prioritize targeted safety interventions.
# Key Questions
 + How do accident patterns differ under various light conditions (daylight vs. twilight vs. dark)? 

+ How do road surface conditions (dry, wet, snow/ice) influence accident frequency and severity? 

+  Which driver behaviours are most associated with severe accidents?
 
+  Which states or districts show higher risk patterns compared to others? 

+ Where should safety interventions be prioritized based on observed patterns?
# Data
  Unfallatlas 2024 dataset contains georeferenced data on road traffic accidents involving personal injury across Germany in 2024. It includes information on: 
  
+ Accident location 

+ Severity level 

+ Road surface and weather conditions 

+ Light and visibility conditions 

+ Driver/road user behaviours contributing to the accident
# Folder Structure
  01 Poject Management: Project brief and deliverables. 
  
  02 Scripts: All relevant project visualizations answering key questions. 
  
  03 Analysis: All project python scripts.
 # Data Cleaning & Preparation

Key preprocessing steps include:

+ Standardization of municipality names

    Handling non-UTF8 characters, German umlauts, encoding fixes.

+ Merging accident data with geospatial AGS identifiers

    Ensuring 1 to 1 mapping between accident rows and German municipality polygons.

+ Creation of rates normalized by population:

  + Accident per 100,000 residents

  + Driver behavior category rates

  + Light condition rates

  + Road surface condition rates

  + Fatality rate

  + Outlier detection & handling

Removed invalid AGS codes, duplicate municipality entries, and geometry mismatches.
# Tools:
+ Python 3.10+
+ Pandas, NumPy
+ Scikit-learn (scaling, KMeans clustering)
+ GeoPandas, Shapely (geospatial data)
+ Matplotlib / Seaborn
+ Tableau (storyboard dashboards)
+ Jupyter Notebook
# Exploratory Data Analysis (EDA)

The EDA examines accident variability across:

Light Conditions

+ Daylight accounts for most accidents across Germany.

+ Darkness shows disproportionately higher driver-error involvement.

Road Surface

+ Wet/slippery surfaces sharply increase loss-of-control and behavior-related crashes, but not necessarily severity.

+ Dry roads produce higher volumes but lower severity.

Driver Behaviors

+ Same-direction and turn/cross collisions are the most common conflict types.

+ Driver-error involvement is notably higher in dense urban traffic.

Regional Variability

+ Urban states show higher accident exposure due to traffic density.

+ Rural states show higher severity due to higher speeds and longer travel distances.
# Clustering Analysis
Goal:
Group municipalities into accident-environment profiles.

Workflow:

Select 15 engineered rate features

Standardize using StandardScaler

Fit KMeans (k=4 optimal from elbow analysis)

Join clusters back to geographic AGS codes

Generate cluster profiles + heatmaps

Final 4 Cluster Profiles
Cluster	Description
Teal – Daylight & Dry Low-Risk Commuter Areas	Stable daylight/dry environments; low-behavioral risk.
Blue – Driver-Error High-Exposure (Mixed Light/Surface)	Urban mixed-condition areas with high driver-error frequency.
Gold – Wet-Surface Crash-Sensitive	High crashes on wet surfaces; loss-of-control common.
Purple – High-Speed / High-Severity Areas	Rural dry-daylight crashes but high severity due to speed.
# Visualizations Created

Municipality-level cluster map

State-level cluster composition

State comparison (NRW vs Brandenburg)

Cluster profile heatmap
# Key Insights

• Most accidents occur in daylight and on dry roads, reflecting routine commuter traffic.

• Darkness and wet conditions contribute less to accident frequency but increase severity where they occur.

• Driver errors and lane-change or turning conflicts dominate across clusters.

• High-severity crashes occur mainly under good light and surface conditions, a result of higher speeds rather than visibility or traction.

• States differ by their dominant accident environments, urban, commuter, wet-sensitive, or high-speed rural.
# Key Recommendations by Cluster

Blue – Driver-Error High-Exposure:
Improve lane markings, intersection lighting, and driver awareness in dense traffic zones.

Gold – Wet-Surface Crash-Sensitive:
Install high-friction pavement and drainage upgrades on wet or slippery road segments.

Teal – Daylight & Dry Low-Risk:
Maintain road quality and markings to preserve current low-risk commuter conditions.

Purple – High-Speed / High-Severity:
Implement speed calming, median barriers, and better curve visibility to reduce fatal crashes.
##  Interactive Tableau Story

View the full interactive dashboard here:  
 **[Tableau Story – Accident Pattern Across Germany 2024](https://public.tableau.com/app/profile/farah.j2084/viz/AccidentPatternAcrossGermany2024/Story1)**  


Citation: Datenquelle: Unfallatlas 2024 (DESTATIS) Dieses Werk ist lizensiert unter der Datenlizenz Deutschland - Namensnennung - Version 2.0 (www.govdata.de/dl-de/by-2-0) 
