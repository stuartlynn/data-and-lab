---
layout: post
title: "Chicago Health Indicators (2005-11)"
date: 2017-07-18 16:41:16
image: /assets/img/
description:
main-class: 'health'
color:
tags:
- health
- polygons
- <500
- smaller areas
- ESDA
- open data
- Census
categories:
twitter_text:
introduction: "Health indicators for Chicago community areas (2005-11)."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the HealthIndicators_withpc Geojson-->
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
  $.getJSON("../data/HealthIndicators_withpc.geojson",function(data){
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

[DOWNLOAD DATA](../data/healthIndicators.zip)

Health indicators for Chicago neighorhoods. Source: [City of Chicago Data Portal.](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu). Data provided by Illinois Department of Public Health (IDPH) and U.S. Census Bureau.

* Observations = 77
* Variables = 31
* Years = 2005-11


|**Variable**|**Description**|
|:-------|:----------|
|area\_num| Community area ID |
|shape\_area| Polygon area |
|shape\_len| Shape length |
|comm\_area| Community area name | 
|BirthRate|Births per 1,000 residents|
|Gener\_Rate|General fertility rate per 1,000 females 15-44|
|LowBi\_ight|Percent of live births with low birth weight|
|Prena\_ster|Percent of live births who had prenatal care beginning in first trimester|
|Prete\_rths|Preterm births as percent of live births|
|TeenB\_Rate|Teen birth rate per 1,000 females age 15-19|
|Assa\_cide|Assault(homicide) per 100,000 people, age adjusted.|
|Breas\_ales|Breast cancer deaths per 100,000 females, age adjusted.|
|Cance\_ites|Cancer deaths per 100,000 people, age adjusted.|
|Color\_ncer|Colorectal cancer deaths per 100,000 people, age adjusted.|
|Diabe\_ated|Diabetes-related deaths per 100,000 people, age adjusted.|
|Firea\_ated|Firearm related deaths per 1000,000 people, age adjusted.|
|Infan\_Rate|Infant mortality rate per 1,000 live births|
|LungCancer|Lung cancer deaths per 100,000 people, age adjusted.|
|Prost\_ales|Prostate cancer deaths per 100,000 males, age adjusted.|
|Strok\_ease|Stroke deaths per 100,000 people, age adjusted.|
|Child\_ning|Childhood blood lead level screening per 1,000 children age 0-6 years|
|Chil\_ing\_1|Childhood lead poisoning per 100|
|Gonor\_ales|Gonorrhea in females, per 100,000 females age 15-44|
|Gono\_ales\_1|Gonorrhea in females, per 100,000 females age 15-44|
|Tuber\_osis|Tuberculosis per 100,000 people|
|Below\_evel|Percent of households below poverty level|
|Crowd\_sing|Percent of occupied housing units|
|Dependency|Percent of persons aged less than 16 or more than 64 years|
|NoHig\_loma|Percent of persons age 25 or higher without high school diploma|
|PerCa\_come|Percapita income, 2011 adjusted dollars|
|Unemp\_ment|Unemployment as a percent of persons aged 16 or older|

Prepared by Jingyuan Zhou. Last updated July 10, 2017. Data provided "as is", no warranties.

