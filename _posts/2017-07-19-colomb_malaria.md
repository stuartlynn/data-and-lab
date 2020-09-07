---
layout: post
title: "Malaria in Colombia (1998)"
date: 2017-07-18 16:10:16
image: /assets/img/
description:
main-class: 'health'
color:
tags:
- health
- polygons
- 500-5,000
- larger areas
- ESDA
- open data
categories:
twitter_text:
introduction: "Malaria Incidence in Colombian municipalities"
---

<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery Â© <a href="http://mapbox.com">Mapbox</a>',
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
  $.getJSON("../data/colmunic1.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    var json = L.geoJson(data);
    json.addTo(map);
    map.fitBounds(json.getBounds());
  });

</script>


[DOWNLOAD DATA](../data/malariacolomb.zip)

Malaria incidence in 1998,  population from 1973, 1985, 1993 censuses, and projected population from 1995 to 2005.            

* Observations = Municipalities: 1,068, Departments: 33
* Variables = 50
* Years = 1973-2005

**Source:**
 Modified from the boundary files downloaded from http://www.cipotato.org/. Malaria incidence in 1998. (Source:   SIVIGILA. Ministerio de Salud, Colombia.There are 3 files for each year     from 1995-2005. Projections from Departamento Administrativo Nacional de Estadastica DANE, Colombia). 

|**File**|**Description**|
|---|---|
|colmunic | Data at administrative level 2 (Counties) |
|coldept | Data at administrative level 1 (States) |


|**Variable**|**Description**|
|---|---|
|	ID	|	Sequencial ID	|
|	ADM0	|	Country name	|
|	ADM1	|	Departmentos=States (Administrative level 1)	|
|	ADM2	|	Municipioss=Counties (Administrative level 2)	|
|	IDDANE	|	DANE (Colombian National Bureau of Statistics) code for counties in numeric format	|
|	DANECODE	|	DANE (Colombian National Bureau of Statistics) code for counties in character format	|
|	CODDEPT	|	DANE (Colombian National Bureau of Statistics) code for states 	|
|	TPyyyy	|	Total population from census in year 'yyyy' (1973, 1985, and 1993 have census population, the remaning years have projected population)	|
|	UPyyyy	|	Urban population from census in year 'yyyy' (1973, 1985, and 1993 have census population, the remaning years have projected population)	|
|	RPyyyy	|	Rural population from census in year 'yyyy' (1973, 1985, and 1993 have census population, the remaning years have projected population)	|
|	MALARI98	|	Malaria incidence in 1998 |                                 

Prepared by Luis Galvis. Last updated June 20, 2005. Data provided "as is," no warranties.

