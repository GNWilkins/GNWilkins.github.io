## Comparing Wisconsin Cities: Madison and Milwaukee
**Project for Advanced GIS course at UMBC**
<br><br>
This project compared the demographics of Madison, WI, and Milwaukee, WI. Population, median household income, and statistics on race and ethnicity for block groups in each city were gathered from the 5-year American Community Survey (ACS).
<br><br>
[Demographics of Madison, WI](../486_Project_3_Comparing_Wisconsin_cities/Madison_webmap_full/qgis2web_2020_05_04-22_09_12_473357/index.html)
  <iframe width="780" height="340" src="../486_Project_3_Comparing_Wisconsin_cities/Madison_webmap/qgis2web_2020_05_04-22_09_12_473357/index.html" frameborder="0" allowfullscreen></iframe>
<br>
[Demographics of Milwaukee, WI](../486_Project_3_Comparing_Wisconsin_cities/Madison_webmap/qgis2web_2020_05_04-22_09_12_473357/index.html)
<iframe width="780" height="340" src="../486_Project_3_Comparing_Wisconsin_cities/Milwaukee_webmap/qgis2web_2020_05_04-22_11_23_595666/index.html" frameborder="0" allowfullscreen></iframe>

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
All data is projected in EPSG 3857 Web Mercator. Charts were generated using [Chart.js](https://www.chartjs.org/)
<br>
Made using R 3.6.2 and QGIS 3.10 (with Stamen Toner Lite and Stamen Watercolor basemaps). Hosted on [Leaflet](https://leafletjs.com/) via the QGIS2web plugin for QGIS.
