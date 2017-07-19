---
layout: post
title: "Chile"
date: 2017-07-19 12:01:16
image: /assets/img/
description:
main-class: 'DEMOGRAPHICS'
color:
tags:
- polygon
- demographics
- research project
- Rates
- Space-time
categories:
twitter_text:
introduction: "A set of recently created labour market areas (LMAs) for Chile."
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the Harmonised_municipalities Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../Harmonised_municipalities.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>

Data provided "as is", no warranties.

A set of recently created labour market areas (LMAs) for Chile, required to analyze spatial labour market activity and provide a framework to guide spatially-explicit employment policy development. The data set includes 62 LMAs, providing full coverage of the Chilean territory, delineated based on optimisation requirements of self-containment, cohesion and homogeneity of a regionalisation algorithm described in Casado-Díaz et al. (2017), using commuting data from the CHilean Migration (CHIM) database (Rowe & Bell, 2013). Data from the 1982, 1992 and 2002 Chilean Housing and Population census were appended to the set of LMAs to produce a geographic information database. The database contains information on the resident population by five-year age groups, sex, labour force status, industry sector and occupation.


Sources:
- Rowe F, & Bell M (2013) <i>Creating an integrated database for the analysis of spatial mobility in Chile</i> (Working Paper 02/2013). Queensland Centre for Population Research, School of Geography, Planning and Environmental Management, The University of Queensland, Brisbane, Australia.											

- Rowe F (2017) The CHilean Internal Migration (CHIM) database: Temporally consistent spatial data for the temporal analysis of internal migration in Chile, REGION											

 Type = polygon shape file

 Variables = 25

 Observations = 304

 Year Range = 1977-2002

 Spatial resolution = low

 Topic = demographics

 Type of sample data = research project

 Rates

 Space-time


|Variable|Description|
|:-------|:----------|
|IDN_1|Unique spatial unit identifier|
|C_REG|Region code|
|REG|Region name|
|C_PROV|Province code|
|PROV|Province name|
|C_MUN|Temporal municipality code|
|MUN|Temporal municipality name|
|Pop_1982, Pop_1992, Pop_2002|1982-1992-2002 census population |
|Age group|0-4	(code: 1), 5-9	(2), 10-14	(3), 15-19	(4), 20-24	(5), 25-29	(6), 30-34	(7), 35-39	(8), 40-44	(9), 45-49	(10), 50-54	(11), 55-59	(12), 60-64	(13,) 65-69	(14), 70-74	(15), 75-79	(16), 80-84	(17), 85+	(18)|
|Gender| Male (code: 1), Female (2)|
|Education|Never attended	(code: 1), Preschool education	(2), Primary education	(3), Secondary education	(4), Higher education	(5)|
|Labour force status|Employed	(code: 1), Unemployed	(2), Not in the labour force	(3)|
|Employment class|Wage earners	(code: 1), Domestic workers	(2), Self-employed	(3), Employers	(4), Unpaid family workers	5)|
|Industry sector|Agriculture	(code: 1), Mining	(2), Manufacturing	(3), Utilities	(4), Construction	(5), Trade	(6), Transport and Communication	(7), Finance	(8), Business Services	(9), Public Administration	(10), Comm & Personal Services	(11)|
|Occupation|Managers (code: 1), Professionals	(2), Technicians	(3), Clerks (4), Tradespeople (5), Agr. & Fish. Workers	(6), Craft workers	(7), Plant operators	(8), Labourers	(9), Armed forces	(10)|
|Per capita wages* | in Chilean pesos|
|Unemployment rate* | in %|
|Cummulative Foreign Direct Investemet (FDI)* |USD millions|
|Exports* |USD millions|
|Housing cost index* |Index 100=1980|
|Housing cost supply* |In number of housing units|
|15-34 age population* |in %|
|Agricultural employment* |in %|
|Owner occupiers*|in %|
|Population* |in number of people|

(*) The Regional variables data files provides information on 10 variables for three five-year census intervals: 1977-82, 1987-92 and 1997-2002		

Note: No information for wages and exports is available for the 1977-82 interval. Cummulative Foreign Direct Investemet corresponds to the sum of all five years in the interval. For detail information on these variables, see Rowe F, (2013) *Spatial labour mobility in a transition economy: Migration and commuting in Chile*, PhD Thesis, School of Geography, Planning and Environmental Management, The University of Queensland.											

Prepared by Joshua Mark for the Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))

 Last updated July 19, 2017.
