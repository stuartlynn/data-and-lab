---
layout: post
title: "AirBnB Chicago 2015"
date: 2017-07-1 16:29:16
image: /assets/img/
description:
main-class: 'HOUSING'
color:
tags:
- polygon
- housing
- census data
- open data
- Rates
categories:
twitter_text:
introduction: 'This database is about Airbnb spots, socioeconomic indicators, and crime by community area in Chicago.'
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the Nepal Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  map.scrollWheelZoom.disable();
  map.touchZoom.disable();
  var enableMapInteraction = function () {
      map.scrollWheelZoom.enable();
      map.touchZoom.enable();
  }
  $('#map').on('click touch', enableMapInteraction);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../data/airbnb_Chicago2015.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    var json = L.geoJson(data);
    json.addTo(map);
    map.fitBounds(json.getBounds());
  });

</script>

Data provided "as is", no warranties.

 This database is about Airbnb spots, socioeconomic indicators, and
crime by community area in Chicago.

 Type = polygon shape file

 Observations = 77

 Variables = 20

 Year range = 2008-2015

 Spatial resolution = medium

 Topic = housing rentals

 Type of sample data = Census/open data

 Rates


|Variable|Description|Source|
|---|---|---|
|community|name of community area|City of Chicago data portal
|AREAID|ID number associated with the community area|City of Chicago data portal
|response\_r|response rate of airbnb host|Airbnb data: [Inside Airbnb](http://insideairbnb.com/get-the-data.html) -- only public available data were used.  The data were collected on October 3rd, 2015.
|accept\_r|acceptance rate of airbnb host|[Inside Airbnb](http://insideairbnb.com/get-the-data.html)|
|rev\_rating|host's rating|[Inside Airbnb](http://insideairbnb.com/get-the-data.html)|
|price\_pp|price per person|[Inside Airbnb](http://insideairbnb.com/get-the-data.html)|
|room\_type|1 is entire home/apartment, 2 is private room, and 3 shared room|[Inside Airbnb](http://insideairbnb.com/get-the-data.html)|
|num\_spots|number of airbnb spots|[Inside Airbnb](http://insideairbnb.com/get-the-data.html)|
|poverty|percent households below poverty|Socioeconomic indicators: [Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2). These indicators were built for the period 2008 to 2012.|
|crowded|percent housing crowded|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|dependency|percent under 18 or over 64 years old|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|without\_hs|percent aged 25+ without high school diploma|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|unemployed|percent unemployed above 16 years old|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|income\_pc|per capita income|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|hardship\_in|hardship index|[Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)
|num\_crimes|total number of crimes|Crime: [Chicago Data Portal](https://data.cityofchicago.org/view/5cd6-ry5g). The crime data include the number of crimes (battery, burglary, gambling, homicide, kidnapping, robbery, stalking, homicide, and theft, among others; murders with data for each victim are not included) and thefts from October 2014 to September 2015 (one year before the Airbnb data).
|num\_theft|total number of thefts|[Chicago Data Portal](https://data.cityofchicago.org/view/5cd6-ry5g)
|population|community area population in 2010|[Census 2010, Chicago Data Portal](https://www.cityofchicago.org/content/dam/city/depts/zlup/Zoning_Main_Page/Publications/Census_2010_Community_Area_Profiles/Census_2010_and_2000_CA_Populations.pdf)|

Prepared by Rodrigo Valdes.

Last updated July 10, 2017.
