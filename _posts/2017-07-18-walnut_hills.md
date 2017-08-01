---
layout: post
title: "Walnut Hills"
date: 2017-07-18 16:45:16
image: /assets/img/
description:
main-class: 'CRIME'
color:
tags:
- polygon
- crime
- research project
- Rates
- Luc Anselin course lab
categories:
twitter_text:
introduction: "Crime data in the Clifton, Walnut Hills, Evanston, and Avondale neighborhoods of Cincinnati, OH for the last 6 months of 2008."
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the walnut_hills Geojson-->
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
  $.getJSON("../data/walnut_hills.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    var json = L.geoJson(data);
    json.addTo(map);
    map.fitBounds(json.getBounds());
  });

</script>

Data provided "as is", no warranties.

Crime data in the Clifton, Walnut Hills, Evanston, and Avondale neighborhoods of Cincinnati, OH for the last 6 months of 2008. From Grubesic, T, R. Wei and A. Murray (2014). [Spatial clustering overview and comparison: accuracy, sensitivity and computational expense.](http://www.tandfonline.com/doi/full/10.1080/00045608.2014.958389) Annals, Association of American Geographers 104, 1134-1156.


 Type = polygon shape file

 Variables = 89

 Observations = 457

 Year Range = 2008

 Spatial resolution = medium

 Topic = crime

 Type of sample data = research project

 Rates

 Luc Anselin course lab

|Variable|Description|
|:-------|:----------|
|BLOCK|Census block|
|TRACT|Census tract|
|COUNTY|5 digit code for the county (Hamilton County, Ohio). Not to be confused with zip code|
|POPULATION|Population on the block|
|MALE, FEMALE|Population on the block broken down by gender|
|AGE\_5, AGE\_5\_TO\_9, AGE\_10\_14, AGE\_15\_19, AGE\_20\_24, AGE\_25\_34, AGE\_35\_44, AGE\_45\_54, AGE\_55\_59, AGE\_60\_64, AGE\_65\_74, AGE\_75\_84, AGE\_85|Population on the block broken down by age|
|MEDIAN\_AGE|Median age on the block|
|AGE\_18, MALE\_18, FEMALE\_18, AGE\_21, AGE\_62, AGE\_65, MALE\_65, FEMALE\_65|Population aged 18 and over, 21 and over etc. Gender breakdowns included for 18-and-over and 65-and-over.|
|F1\_RACE|Number of people who marked a race on the survey|
|WHITE, BLACK, AMINDIAN, ASIAN, HAWAIIAN, OTHER\_RACE|Population breakdown by race|
|F2\_RACES|Number of people who did not mark any race on the survey|
|AP\_WHITE, AP\_BLACK, AP\_AMINDIA, AP\_ASIAN, AP\_HAWAIIA, AP\_OTHER|Population breakdown by race|
|AP\_HISPANI, NOT\_HISPAN|Population breakdown by Hispanic and Non-Hispanic|
|NH\_WHITE|Non-Hispanic white population|
|IN\_HOUSEHO|Population living in households|
|GROUP\_QUAR|Population living in group quarters instead of traditional households|
|GQ\_INSTU, GQ\_NONINST|Population broken down by institutional and non-institutional|
|HOUSEHOLDS|Number of households|
|HH\_FAMILY|Number of family households|
|HH\_NONFAMI|Number of non family households|
|AVG\_HHSIZE|Average household size|
|AVG\_FAMSIZ|Average family size|
|HSNG\_UNITS|Number of housing units|
|HU\_OCCUPIE, HU\_VACANT|Number of housing units broken down by occupied and vacant|
|OCCHU\_OWNE, OCCHU\_RENT|Occupied housing units broken down by owner or renter occupied|
|OWNER\_SIZE, RENTER\_SIZ|Average household size of owner and renter occupied housing units|
|DENSITY|Population density|
|BURGLARY, ASSAULT, THEFT|Counts of burglary, assault, and theft|
|BURG\_D, ASSALT\_D, THEFT\_D, BURG\_D1, BURG\_D2|Crime dummy variables: '1' if there is at least 1 incident, '0' otherwise.|

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))
 Last updated July 6, 2017.
