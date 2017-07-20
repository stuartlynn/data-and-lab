---
layout: post
title: "Chilean Internal Migration"
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
introduction: "A temporally consistent framework for the analysis of internal migration over a period covering twenty-five years from 1977 to 2002."
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

This dataset presents the CHilean Internal Migration database which provides a temporally consistent framework for the analysis of internal migration over a period covering twenty-five years from 1977 to 2002. Specifically, it offers a hierarchical system of 304 municipalities, 51 provinces and 13 regions, and 10 occupational groups and 11 industrial sectors which are temporally consistent over the 1977-82, 1987-92 and 1997-2002 census intervals.

Sources:
- Rowe F, & Bell M (2013) <i>Creating an integrated database for the analysis of spatial mobility in Chile</i> (Working Paper 02/2013). Queensland Centre for Population Research, School of Geography, Planning and Environmental Management, The University of Queensland, Brisbane, Australia.											

- Rowe F (2017) The CHilean Internal Migration (CHIM) database: Temporally consistent spatial data for the temporal analysis of internal migration in Chile, REGION											

 Type = polygon shape file

 Variables = 10

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
|Per capita wages* | in Chilean pesos|
|Unemployment rate* | in %|
|Cumulative Foreign Direct Investment (FDI)* |USD millions|
|Exports* |USD millions, FOB|
|Housing cost index* |Index 100=1980|
|Housing cost supply* |In number of housing units|
|15-34 age population* |in %|
|Agricultural employment* |in %|
|Owner occupiers*|in %|
|Population* |in number of people|

(*) The Regional variables data files provides information on 10 variables for three five-year census intervals: 1977-82, 1987-92 and 1997-2002		

Note: No information for wages and exports is available for the 1977-82 interval. Cumulative Foreign Direct Investment corresponds to the sum of all five years in the interval. For detail information on these variables, see Rowe F, (2013) *Spatial labour mobility in a transition economy: Migration and commuting in Chile*, PhD Thesis, School of Geography, Planning and Environmental Management, The University of Queensland.		


Prepared by Joshua Mark for the Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))

 Last updated July 19, 2017.
