---
layout: post
title: "San Francisco crime"
date: 2017-07-18 16:52:16
image: /assets/img/
description:
main-class: 'CRIME'
color:
tags:
- point shape file
- crime
- open data
- Luc Anselin course lab
categories:
twitter_text:
introduction: "Crimes reported to San Francisco police, for July 2012 to December 2012."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the SFcartheft_july12 Geojson-->
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
  $.getJSON("../data/SFcartheft_july12.geojson",function(data){
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

Crimes reported to San Francisco police, for July 2012 to December 2012\. Separate files for each month and category of crime.
File names indicate the month, e.g. **SFcartheft_aug12**
Source: ["Crime Incidents from 1 Jan 2003", City of San Francisco Open Data Portal](https://data.sfgov.org/Public-Safety/Map-Crime-Incidents-from-1-Jan-2003/gxxq-x39z)


Type = point shape file.

Variables = 16

Year = 2012

Spatial resolution = high

Topic = crime

Type of sample data = open data

Luc Anselin course lab

Observations vary by month and category:

SFcartheft_july12 = 607

SFcartheft_aug12 = 553

SFcartheft_sep12 = 562

SFcartheft_oct12 = 561

SFcartheft_nov12 = 568

SFcartheft_dec12 = 533


SFdrugs_july12 = 610

SFdrugs_aug12 = 671

SFdrugs_sep12 = 647

SFdrugs_oct12 = 688

SFdrugs_nov12 = 639

SFdrugs_dec12 = 643



SFrob_july12 = 385

SFrob_aug12 = 497

SFrob_sep12 = 438

SFrob_oct12 = 483

SFrob_nov12 = 497

SFrob_dec12 = 461



SFvand_july12 = 562

SFvand_aug12 = 576

SFvand_sep12 = 593

SFvand_oct12 = 694

SFvand_nov12 = 536

SFvand_dec12 = 470

| Variable | Description |
|--
| IncidntNum, IncidntN_1 | Unique number for each incident report |
| Category | Vehicle theft |
| Descript | Description of the crime |
| DayOfWeek | day of the week that crime was reported |
| PdDistrict | Police district |
| Resolution | Outcome of the report, e.g. None, Arrest, Unfounded etc |
| Location | Street address where the crime occurred |
| Date | Date of the report |

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))
Last updated July 3, 2017.
