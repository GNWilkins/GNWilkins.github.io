## Comparing Wisconsin Cities: Madison and Milwaukee
**Project for Advanced GIS course at UMBC**
<br><br>
This project compared the demographics of Madison, WI, and Milwaukee, WI. Population, median household income, and statistics on race and ethnicity 
for block groups in each city were gathered from the 5-year American Community Survey (ACS).
[Madison, WI](../486_project_2_Wisconsin/New_Madison_webmap/qgis2web_2020_04_19-22_34_43_006919/index.html)
<br>
[<image src="../486_project_2_Wisconsin/images/Madison_webmap_thumbnail.PNG?raw=true"/>](../486_project_2_Wisconsin/New_Madison_webmap/qgis2web_2020_04_19-22_34_43_006919/index.html)

<br>
[Milwaukee, WI](../486_project_2_Wisconsin/New_Milwaukee_webmap/qgis2web_2020_04_19-22_35_28_353110/index.html)
<br>
[<image src="../486_project_2_Wisconsin/images/Milwaukee_webmap_thumbnail.PNG?raw=true"/>](../486_project_2_Wisconsin/New_Milwaukee_webmap/qgis2web_2020_04_19-22_35_28_353110/index.html)

<br><br>
Census data was gathered using tidycensus in R, using code like the example shown:
<pre>
  <code>
Madison_census <- get_acs(geography = "block group",
              variables = c(population = "B01003_001",
                            medincome = "B19013_001",
                            white = "C02003_003",
                            black = "C02003_004",
                            hispanic = "B03002_012",
                            asian = "C02003_006"), 
              state = "WI",
              county = "Dane",
              year = 2018,
              survey = "acs5",
              geometry = TRUE, 
              output="wide",
              )
  </code>
</pre>
All data is projected in EPSG 3857 Web Mercator.
<br>
Made using R 3.6.2 and QGIS 3.10 (with Stamen Toner Lite and Stamen Watercolor basemaps).
