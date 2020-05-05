# GES 486 Project 2 (By Gabriel Wilkins)
The front-end of this project can be found [here](https://gnwilkins.github.io/486_project_2_Wisconsin/Wisconsin_2020_primary.html)

## Topic
Comparing the cities of Madison, WI, and Milwaukee, WI. Looked at various population demographics and access to voting places during the 2020 primary election.

## Data
Data was gathered from:
<br>
[WTMJ Milwaukee](https://www.tmj4.com/news/local-news/these-are-the-five-in-person-voting-centers-in-milwaukee-open-for-wisconsins-spring-primary-tuesday) for the addresses of Milwaukee voting places on April 7th, 2020.
<br>
[Wisconsin Department of Natural Resources Open Data Portal](https://data-wi-dnr.opendata.arcgis.com/search?tags=transportation) for major and county roads througout Wisconsin.
<br> 
[City of Madison Open Data Portal](https://data-cityofmadison.opendata.arcgis.com/datasets/polling-places) for polling places in Madison for April 7th, 2020.
<br>
Census data (block groups from the most recent American Community Survey 5-year data) was gathered using tidycensus in R, using code like the example shown:
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
## Analysis
Select columns from the census data were gathered in R using code such as:
<pre>
  <code>
# Use WGS84 UTM Zone 16N
Madison_census_utm <- st_transform(Madison_census, 32616)

# Calculate total population
total_pop <- sum(Madison_census_utm$populationE)

# Calculate share of population
Madison_census_utm$pop_share <-
  Madison_census_utm$populationE / total_pop

#Calculate white share of population
Madison_census_utm$PerWhte <-
  Madison_census_utm$whiteE / Madison_census_utm$populationE
  </code>
</pre>
Data was then transformed and analyzed in QGIS (v3.10), where, for each Madison and Milwaukee cities, travel distance to polling places was calculated using the Open Route Service (ORS) Tools plugin.
Three different versions of each city's census blocks were developed, showing:
 <ul>
  <li>Population</li>
  <li>Percentage of population that is non-white</li>
  <li>Median household income</li>
</ul>
<br>
<b>Outputs</b>
<br>
Two different Leaflet elements were made, one for each city.
Ideally, they would both be embedded in the same webpage for ease of comparison, but as of yet I have not had the time to devote to figuring out how to do that.
<br>
Also ideally, there would have been images of lines pulled from tweets made at and near polling places on April 7th, 2020, particularly in Milwaukee.
But unfortunately, I started trying to gather such tweets after the (previously unknown to me) 7-day limit on Twitter's search API.


