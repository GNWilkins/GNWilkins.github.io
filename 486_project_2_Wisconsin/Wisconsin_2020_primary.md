## Comparing Wisconsin Cities: Madison and Milwaukee
**Project for Advanced GIS course at UMBC**
<br><br>
This project looked compared select census data and access to polling sites (during the 2020 primary) between Madison, WI, and Milwaukee, WI.  
Each map has four different data layers:  
 <ul>
  <li>Voting locations for each city on April 7th, 2020</li>
  <li>Census block groups from the most recent American Community Survey 5-year data colored by:
    <ul>
      <li>Population</li>
      <li>Percentage of population that is non-white</li>
      <li>Median household income</li>
    </ul>
  </li>
</ul> 
[Madison, WI](../486_project_2_Wisconsin/New_Madison_webmap/qgis2web_2020_04_19-22_34_43_006919/index.html)
<br>
[<image src="../486_project_2_Wisconsin/images/Madison_webmap_thumbnail.PNG?raw=true"/>](../486_project_2_Wisconsin/New_Madison_webmap/qgis2web_2020_04_19-22_34_43_006919/index.html)

<br>
[Milwaukee, WI](../486_project_2_Wisconsin/New_Milwaukee_webmap/qgis2web_2020_04_19-22_35_28_353110/index.html)
<br>
[<image src="../486_project_2_Wisconsin/images/Milwaukee_webmap_thumbnail.PNG?raw=true"/>](../486_project_2_Wisconsin/New_Milwaukee_webmap/qgis2web_2020_04_19-22_35_28_353110/index.html)
<br>
Data was gathered from:
<br>
[WTMJ Milwaukee](https://www.tmj4.com/news/local-news/these-are-the-five-in-person-voting-centers-in-milwaukee-open-for-wisconsins-spring-primary-tuesday)
<br>
[Wisconsin Department of Natural Resources Open Data Portal](https://data-wi-dnr.opendata.arcgis.com/search?tags=transportation)
<br> 
[City of Madison Open Data Portal](https://data-cityofmadison.opendata.arcgis.com/datasets/polling-places)
<br>
Census data was gathered using tidycensus in R, using code like the example shown:
<pre>
  <code>
Madison_census <- get_acs(geography = "block group",
              variables = c(population = "B01003_001",
                            medincome = "B19013_001",
                            white = "C02003_003"), 
              state = "WI",
              county = "Dane",
              year = 2018,
              survey = "acs5",
              geometry = TRUE, 
              output="wide",
              )
  </code>
</pre>
All data is projected in WGS 84 Zone 16N.
<br>
Made using QGIS 3.10 (with Stamen Toner Lite).
