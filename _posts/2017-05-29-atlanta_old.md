---
layout: post
title: "Atlanta Homicides 1980s-90s"
date: 2017-05-29 15:00:57
image: '/assets/img/'
description:
main-class: 'crime'
color:
tags:
- crime
- polygons
- rates
- space-time
- <500
- ESDA
- regression
- research
categories:
twitter_text:
introduction: '1980s-90s homicides and socio-economics in Atlanta, GA'
---
<script>
var map = L.map('map');
L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
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
$.getJSON("../data/atlanta.geojson",function(data){
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

[DOWNLOAD DATA](../data/atlanta_hom.zip)


Homicides and selected socio-economic characteristics for counties surrounding Atlanta, GA. Data aggregated for three time periods: 1979-84 (steady decline in homicides), 1984-88 (stable period), and 1988-93 (steady increase in homicides). Download the file [here](../data/atlanta_hom.zip).

* Projection: unprojected, lat-lon
* Observations = 90
* Variables = 23
* Years 1980s-90s


**Source**
S. Messner, L. Anselin, D. Hawkins, G. Deane, S. Tolnay, R. Baller (2000). An Atlas of the Spatial Patterning of County-Level Homicide, 1960-1990. Pittsburgh, PA, [National Consortium on Violence Research (NCOVR)](https://www.nttac.org/index.cfm?event=projectDetails&id=339).

|**Variable**|**Description**|
|---|---|
|NAME | county name|
|STATE_NAME | state name|
|STATE_FIPS | state FIPS code (character)|
|CNTY_FIPS | county FIPS code (character)|
|FIPS | combined state and county FIPS code (character)|
|STFIPS | state FIPS code |
|COFIPS | county FIPS code |
|FIPSNO | fips code as numeric variable|
|HR7983 | homicide rate per 100,000 (1979-83)|
|HR8487 | homicide rate per 100,000 (1984-87)|
|HR8895 | homicide rate per 100,000 (1988-95)|
|HC7983 | homicide count (1979-83)|
|HC8487 | homicide count (1984-87)|
|HC8895 | homicide count (1988-95)|
|PO7983 | population total (1979-83)|
|PO8487 | population total (1984-87)|
|PO8895 | population total (1988-95)|
|PE77 | police expenditures per capita, 1977|
|PE82 | police expenditures per capita, 1982|
|PE87 | police expenditures per capita, 1987|
|RDAC80 | resource deprivation/affluence composite variable, 1980|
|RDAC85 | resource deprivation/affluence composite variable, 1985|
|RDAC90 | resource deprivation/affluence composite variable, 1990|

Prepared by Luc Anselin. Last updated September 10, 2004. Data provided "as is," no warranties.
