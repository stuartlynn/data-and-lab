---
layout: post
title: "San Francisco Crime Counts (2012)"
date: 2017-07-18 16:46:16
image: /assets/img/
description:
main-class: 'crime'
color:
tags:
- polygons
- 500-5,000
- smaller areas
- open data
- ESDA
- rates
categories:
twitter_text:
introduction: "Count of robberies, drugs/narcotics possession or sale, vehicle theft, and vandalism by San Francisco block group (06-12/2012)."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the SFCrime_blocks Geojson-->
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
$('#map').on('mouseout', function(){ map.scrollWheelZoom.disable();});

  var smallIcon = L.icon({
         iconUrl: 'http://www.hckrecruitment.nic.in/images/blue.png',
         iconSize: [16, 16], // size of the icon
         });

   function onEachFeature(feature, layer) {
     //console.log(feature);
     var txt = "";
     for (var fname in feature.properties) {
       txt += fname;
       txt += " : ";
       txt += feature.properties[fname];
       txt += "<br/>";
     }
     layer.bindPopup(txt);
   }


  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../data/SFCrime_blocks.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    var json = L.geoJson(data, {
      pointToLayer: function(feature, latlng) {
        
        return L.marker(latlng, {
          icon: smallIcon
        });
      },
      onEachFeature: onEachFeature
    });
    json.addTo(map);
    map.fitBounds(json.getBounds());
  });

</script>

[DOWNLOAD DATA](https://s3.amazonaws.com/geoda/data/SFCrime_July_Dec2012.zip)

Population and incidents of robberies, drugs/narcotics possession or sale, vehicle theft, and vandalism for July 1 to December 31, 2012, aggregated to 2010 block groups. 

* Observations = 579
* Variables = 15
* Years = 2010 and 2012


**Data Source:** 
San Francisco Police Department Crime Incident Reporting System
* http://www.sfgov.org
* Crime Incidents: https://data.sfgov.org/Public-Safety/Crime-Incidents/snsg-xkfg
* SFPD Plots: https://data.sfgov.org/Public-Safety/SFPD-Crime-Reporting-Plots-Zipped-Shapefile-Format/5aii-qc4e

**License:**
* Creative Commons license (CC0 1.0 Universal)
* http://creativecommons.org/publicdomain/zero/1.0/legalcode

**Data Extracted on January 10, 2013:**
* Incidents of robberies, drugs/narcotics possession or sale, vehicle theft, and vandalism for July 1 to December 31, 2012 (4 separate point shapefiles).
* One polygons shapefile for SFPD reporting plots that these data were aggregated to.

|Variable|Description|Source
|---|---|---|
|CENSUSAREA|Area in square miles|2010 Census
|GEO\_displa|Unique census tract identifier|2010 Census
|Population|Population within the area|2010 Census
|Vandalism|Incidents of vandalism in each area|San Francisco Police Department Crime Incident Reporting System
|Robbery|Incidents of robbery in each area|San Francisco Police Department Crime Incident Reporting System
|Drugs|Incidents of drugs in each area|San Francisco Police Department Crime Incident Reporting System
|Car Theft|Incidents of car theft in each area|San Francisco Police Department Crime Incident Reporting System

Prepared by ([Center for Spatial Data Science](https://spatial.uchicago.edu/)). Updated July 10, 2017. Data provided "as is," no warranties.
