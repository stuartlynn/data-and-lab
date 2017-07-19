---
layout: post
title: "Chicago supermarkets"
date: 2017-07-18 16:55:16
image: /assets/img/
description:
main-class: 'COMMERCE'
color:
tags:
- point shape file
- Commerce
- open data
- Luc Anselin course lab
categories:
twitter_text:
introduction: "Grocery stores in Chicago, IL as of 2015. Scraped from Google Maps in 2015."
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the chicago_sup Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../chicago_sup.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>


Data provided "as is", no warranties.

Grocery stores in Chicago, IL as of 2015. Scraped from Google Maps in 2015.



 Type = point shape file.

 Variables = 14

 Observations = 149

 Year = 2015

 Topic = Commerce

 Type of sample data = Open data

 Luc Anselin course lab

|Variable|Description
|--
|Field4|Street address
|Field5|Name of the store
|Category|New stores are marked "New," rest are left blank.

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))
 Last updated January 14, 2017.
