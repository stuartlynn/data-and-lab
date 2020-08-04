---
layout: post
title: "2015 Chicago supermarkets"
date: 2017-07-18 16:55:16
image: /assets/img/
description:
main-class: 'economics'
color:
tags:
- economics
- points
- <500
- ESDA
- open data
- Anselin lab
categories:
twitter_text:
introduction: "2015 Chicago grocery stores (scraped from Google Maps)."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the chicago_sup Geojson-->
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
  $.getJSON("../data/chicago_sup.geojson",function(data){
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

[DOWNLOAD DATA](../data/grocery.zip)


Grocery stores in Chicago, IL as of 2015. Scraped from Google Maps in 2015.

* Variables = 14
* Observations = 149
* Year = 2015


|Variable|Description
|--
|OBJECTID\_1|
|OBJECTID|
|OBJECTID\__|
|Field1|
|Field2|
|Field3|
|Field4|Street address
|Field5|Name of the store
|Category|New stores are marked "New," rest are left blank.
|NEAR\_FID|
|NEAR\_DIST|
|NEAR\_X|
|NEAR\_Y|

Prepared by ([Center for Spatial Data Science](https://spatial.uchicago.edu/))
Last updated January 14, 2017. Data provided "as is," no warranties.

