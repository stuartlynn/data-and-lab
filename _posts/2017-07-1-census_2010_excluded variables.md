---
layout: post
title: "Denver foreclosures"
date: 2017-07-1 16:39:16
image: /assets/img/
description:
main-class: 'HOUSING'
color:
tags:
- polygon
- housing
- open data
- Rates
categories:
twitter_text:
introduction: "Demographics of Denver neighborhoods from 2010."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the census_2010_excluded Geojson-->
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
         iconUrl: '../assets/img/icons/blue.png',
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
  $.getJSON("../data/census_2010_excluded.geojson",function(data){
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

Data provided "as is", no warranties.

 Demographics of Denver neighborhoods from 2010. Source: [Denver data portal](https://www.denvergov.org/opendata/dataset/city-and-county-of-denver-census-neighborhood-demographics-2010).


 Type = polygon shapefile

 Observations = 75

 variables = 55

 Year = 2010

 Spatial resolution = medium

 Topic = demographics and housing

 Type of sample data = open data

 Rates

|Variable|Explanation|
|:-------|:----------|
|NBRHD\_NAME|Neighborhood name|
|POPULATION|Population in 2010|
|HISPANIC\_2, WHITE\_2010, BLACK\_2010, NATIVEAM\_2, ASIAN\_2010, HAWPACIS\_2, OTHER\_2010, TWO\_OR\_MOR|Population broken down by race. Hispanic, white, black, Native American, Asian, Hawaiian/Pacific Islander, other, two or more.|
|PCT\_HISPAN, PCT\_WHITE, PCT\_BLACK, PCT\_AMERIN, PCT\_ASIAN, PCT\_HAW\_PA, PCT\_OTHER\_, PCT\_TWO\_OR|race, as percent of total population. Hispanic, white, black, Native American, Asian, Hawaiian/Pacific Islander, other, two or more.|
|MALE, FEMALE|Population broken down by gender|
|AGE10\_14, AGE15\_17, AGE18\_19, AGE60\_61, AGE62\_64, AGE\_0\_TO\_9, AGE20\_29, AGE30\_39, AGE40\_49, AGE50\_59, AGE\_80\_PLU, AGE\_LESS\_1, AGE\_65\_PLU|Population breakdown by age|
|PCT\_LESS\_1, PCT\_65\_PLU|Percent of population under 1 and over 65 years of age.|
|NUM\_HOUSEH|Number of households|
|ONE\_PERSON, TWO\_PLUS|Households broken down by number of people|
|FAMILY\_HHL|Number of family households|
|HUSB\_WIFE, OTHER\_FAMI, MALE\_SINGLE, FEMAL\_SING, NON\_FAMILY|Family households broken down by household head type.|
|GROUP\_QUAR|Population in group quarters|
|GQ\_INSTITU, GQ\_NONINST|Residents of group quarters: institutional (correctional, nursing, etc.) and non-institutional (military, college, etc.)|
|HOUSING\_UN|Number of housing units|
|OCCUPIED\_H|Number of occupied housing units|
|VACANT\_HU|Number of vacant housing units|
|HU\_OWNED|Number of owner-occupied housing units|
|HU\_RENTED|Number of renter-occupied housing units|

Prepared by Leith McIndewar.

Last updated July 10, 2017
