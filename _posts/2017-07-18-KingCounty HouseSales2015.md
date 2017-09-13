---
layout: post
title: "King County House Sales 2015"
date: 2017-07-18 16:31:16
image: /assets/img/
description: "House sale prices for King County, which includes Seattle."
main-class: 'HOUSING'
color:
tags:
- point shape files
- house sales
- open data
categories:
twitter_text:
introduction: "This dataset contains house sale prices for King County, which includes Seattle. It includes homes sold between May 2014 and May 2015."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the KingCountyHouseSales2015 Geojson-->
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
  $.getJSON("../data/KingCountyHouseSales2015.geojson",function(data){
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

 This dataset contains house sale prices for King County, which includes Seattle. It includes homes sold between May 2014 and May 2015.
 It's a great dataset for evaluating simple regression models. Source here: [https://www.kaggle.com/harlfoxem/housesalesprediction/discussion](https://www.kaggle.com/harlfoxem/housesalesprediction/discussion)


 Type = point shape file

 Observations = 21613

 Variables = 21

 Year = 2012-2015

 Spatial resolution = high

 Topic = house sales

 Type of sample data = open data

|Variable|Description|
|:-------|:----------|
|date|date sold|
|price|sale price|
|bedrooms|number of bedrooms|
|bathrooms|number of bathrooms|
|sqft\_\_ving|size of living area in square feet|
|sqft\_lot|size of the lot in square feet|
|floors|number of floors|
|waterfront|'1' if the property has a waterfront, '0' if not.|
|view|An index from 0 to 4 of how good the view of the property was ([definition source](https://rstudio-pubs-static.s3.amazonaws.com/155304_cc51f448116744069664b35e7762999f.html))|
|condition|condition of the house, ranked from 1 to 5|
|grade|Classification by construction quality which refers to the types of materials used and the quality of workmanship. Buildings of better quality (higher grade) cost more to build per unit of measure and command higher value. ([definition source](http://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r))|
|sqft\_above|square feet above ground|
|sqft\_\_ment|square feet below ground|
|yr\_built|year built|
|yr\_re\_ated|year renovated. '0' if never renovated|
|zipcode|5 digit zip code|
|lat, long|latitude and longitude|
|squft\_\_ng15|average size of closest 15 houses, in square feet|
|sqft\_lot15|average size of the closest 15 houses' lots, in square feet|

Prepared by the Center for Spatial Data Science [http://spatial.uchicago.edu/](http://spatial.uchicago.edu/).

 Updated July 10, 2017
