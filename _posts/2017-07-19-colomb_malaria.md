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


[DOWNLOAD DATA](https://s3.amazonaws.com/geoda/data/malariacolomb.zip)

Malaria incidence and population in Colombian municipalities from 1973, 95, 93 censuses and projections until 2005.            

* Observations = Municipalities: 1,068, Departments: 33
* Variables = 50
* Years = 1973-2005

**Source:**
 Modified from the boundary files downloaded from http://www.cipotato.org/. Malaria incidence in 1998. (Source:   SIVIGILA. Ministerio de Salud, Colombia. There are 3 files for each year     from 1995-2005. Projections from Departamento Administrativo Nacional de Estada­stica DANE, Colombia). 

|**File**|**Description**|
|---|---|
|colmunic.shp/shx/dbf | Malaria incidence and  population from 1973, 1985, 1993 censuses and projections until 2005 (Administrative level 2)|
| coldept.shp/shx/dbf | Data for Colombian departments (Administrative level 1) |


|**Variable**|**Description**|
|---|---|
| IDÂ                                   | Sequential ID                        |
| ADM1                                 | Departments (Administrative level 1) |
| ADM2                                 | Municipalities (Administrative level 2)  |
| CODDEPT                              | DANE code for departments            |
| DANECODE                             | DANE code for municipalities         |
| IDDANE                               | DANE code for municipalities in numeric format |
| TP1973                               | Total population from census in 1973 |
| UP1973                               | Urban population form census in 1973 |
| RP1973                               | Rural population from census in 1973 |
| TP1985                               | Total population from census in 1985 |
| UP1985                               | Urban population form census in 1985 |
| RP1985                               | Rural population from census in 1985 |
| TP1993                               | Total population from census in 1993 |
| UP1993                               | Urban population form census in 1993 |
| RP1993                               | Rural population from census in 1993 |
| MALARI98                             | Malaria incidence in 1998. |
| TPyyyy                               | Total population projected in year    yyyy    |
| UPyyyy                               | Urban population projected in year    yyyy    |
| RPyyyy                               | Rural population projected in year   yyyy     |
                                    

Prepared by Luis Galvis. Last updated June 20, 2005. Data provided "as is," no warranties.

