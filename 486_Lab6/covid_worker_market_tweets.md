## Late March, 2020 Twitter Behavior Related to COVID-19
**Lab Project for Advanced GIS course at UMBC**
<br><br>
This project gathered data from Twitter to investigate the frequency and distribution of tweets related to COVID-19 as well as workers or markets.
The number of tweets from March 25th-27th 2020 within each county, independent city, and the District of Columbia were totaled.
<br>
Tweets about COVID-19 (those mentioning 'covid' or 'coronavirus') are displayed in circles sized in proportion to the total number.
Tweets about workers (those mentioning 'worker', 'unemployed', or 'laid-off') were subtracted from tweets about markets (those mentioning 'market', 'stock market', or 'bailout'),
and the difference is displayed using a diverging color scheme.

<br><br>
The first map is colored based on the number of emergency health services (EMS) located within each census block group. The location of each hospital is also displayed, and the lines show the distance from each recognized population center to the hospital closest to it.
[<image src="../project1_486/images/West_Virginia_health_access_map.JPG?raw=true"/>](../pdf/G_Wilkins_WV_healthcare_services.pdf)
<br><br>
The second map focuses on Charleston, West Virginia, displaying the population of census blocks in and around the city, as well as the location of nearby hospitals. A network analysis was performed using the road network data, and iso-areas are displayed which indicate the travel distance along this road network needed to reach this hospital, up to 5 kilometers.
[<image src="../project1_486/images/Charleston_hospitals_map.JPG?raw=true"/>](../pdf/G_Wilkins_Charleston_Hosptials.pdf)
<br>
Data was gathered from the [West Virginia GIS Technical Center](http://wvgis.wvu.edu/data/data.php).
<br>
All data is projected in NAD83 UTM 17N.
<br>
Made using QGIS 3.10 (with Google Satellite).