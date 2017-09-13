---
layout: post
title: "contracts_emp_by_year NTA"
date: 2017-07-18 16:38:16
image: /assets/img/
description:
main-class: 'GOVERNMENT CONTRACTS'
color:
tags:
- polygon
- government contracts
- research project
- Rates
- Space-time
categories:
twitter_text:
introduction: "This file contains information on the allocation of government contracts in New York City across 195 NTAs (neighborhood tabulation areas) over a ten-year period."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the contracts_emp_by_year_nta Geojson-->
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
  $.getJSON("../data/contracts_emp_by_year_nta.geojson",function(data){
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

 This file contains information on the allocation of government contracts in New York City across 195 NTAs (neighborhood tabulation areas) over a ten-year period.
 From Marwell, Nicole P.; Gullickson, Aaron (June 2013). [Inequality in the Spatial Allocation of Social Services: Government Contracts to Nonprofit Organizations in New York City](http://www.journals.uchicago.edu/doi/abs/10.1086/670910): Social Service Review. 87(2): 319-353. The University of Chicago Press.


 Type = polygon shape file

 Observations = 195

 Variables = 54

 Year = 2002-2012

 Spatial resolution = medium

 Topic = government contracts

 Type of sample data = research project

 Rates

 Space-time

|Variable|Description|
|:-------|:----------|
|borocode|number associated with the NYC borough|
|ntaname|New York City NTA (Neighborhood Tabulation Area) name|
|boroname|name of the NYC borough|
|ntacode|code associatd with the NTA|
|cnt2002 to cnt2012|number of contracts operational per year (2002-2012)|
|dol2002 to dol2012|dollars available per year (2002-2012)|
|POPTOT|Population of the NTA|
|delcnt2005 to deldol 2012|Change in contracts operational between the two year periods, (YR , YR-1) and (YR-2, YR-3)|
|deldol2005 to deldol2012|Change in dollars available between the two year periods, (YR , YR-1) and (YR-2, YR-3)|
|cpdl\_5, cpdl\_7, cpdl\_10, cpdl\_12|Per capita change in dollars available between the two year periods, (yr , yr-1) and (yr-2, yr-3). 5 indicates 2005, 7 indicates 2007, etc.|
|rdct\_5, rdct\_7, rdct\_10, rdct\_12|Rate of change in contracts operational between the two year periods, (yr , yr-1) and (yr-2, yr-3)|
|rddl\_5, rddl\_7, rddl\_10, rddl\_12|Rate of change in dollars available between the two year periods, (yr , yr-1) and (yr-2, yr-3)|
|cpct\_5, cpct\_7, cpct\_10, cpct\_12|Per capita change in contracts operational between the two year periods, (yr , yr-1) and, (yr-2, yr-3)|

Prepared by the Center for Spatial Data Science [http://spatial.uchicago.edu/](http://spatial.uchicago.edu/).

Updated July 10, 2017
