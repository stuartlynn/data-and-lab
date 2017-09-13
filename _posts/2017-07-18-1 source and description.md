---
layout: post
title: "Abandoned vehicles"
date: 2017-07-18 16:48:16
image: /assets/img/
description:
main-class: 'POLICE'
color:
tags:
- delimited text file
- crime
- open data
- Luc Anselin course lab
categories:
twitter_text:
introduction: "Information about abandoned vehicles in Chicago, Illinois. Includes all open abandoned vehicle service complaints made to 311 since January 2011, and all requests completed since January 1 2011."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the Nepal Geojson-->
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
  $.getJSON("../data/Nepal.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>
Data provided "as is," no warranties.

Information about abandoned vehicles in Chicago, Illinois. Includes all open abandoned vehicle service complaints made to 311 since January 2011, and all requests completed since January 1 2011.
Retrieved from the City of Chicago Data Portal on August 15 2016. [https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6)


 Type = delimited text file

 Observations = 137867

 Variables = 21

 Year range = 2011-2015

 Spatial resolution = high

 Topic = crime

 Type of sample data = Open data

 Luc Anselin course lab

|Variable|Description|
|---
|Creation Date|Date that the complaint was made|
|Status|Status of the request. Open or complete.
|Completion Date|Date the request was completed. Left blank if not completed.
|Service Request Number|Unique identifier for each service request.
|Type of Service Request|Abandoned Vehicle Complaint for all entries.
|License Plate|License plate number and sometimes a description (state, color). Some entries did not include a plate number.
|Vehicle Make/Model|The make of the vehicle. Many entries only included the make, not the model.
|Vehicle Color|Color of the vehicle
|Current Activity|Either place seven day sticker or FVI - Outcome
|Most Recent Action|The most recent action taken on this vehicle
|How Many Days Has The Vehicle Been Reported as Parked?|Number of days the vehicle has been reported as parked
|Street Address|Street Address where the vehicle was found
|ZIP Code|Five digit zip code corresponding to the address
|X Coordinate|X coordinate of the address
|Y Coordinate|Y coordinate of the address
|Ward|Aldermanic ward (1-50) corresponding to the address
|Police District|Police district (1-25) corresponding to the address
|Community Area|Community area (1-77) corresponding to the address
|Latitude|Latitude corresponding to address
|Longitude|Longitude corresponding to address
|Location|Coordinates of the location in format of (Latitude, Longitude)|

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))

 Last updated July 10, 2017.
