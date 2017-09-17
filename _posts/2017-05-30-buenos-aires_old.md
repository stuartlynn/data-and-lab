---
layout: post
title: "Buenos Aires 1999 Elections"
date: 2017-05-30 15:39:41
image: '/assets/img/'
description:
main-class: 'POLITICS'
color:
tags:
- polygons
- <500
- larger areas
- ESDA
categories:
twitter_text:
introduction: '1999 Elections for Argentinean Congress'
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
  $.getJSON("../data/buenos_aires.geojson",function(data){
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
Selected Electoral Data for the 1999 National Elections, Argentine Congress (Lower House). 

Download the file [here](https://s3.amazonaws.com/geoda/data/buenosaires.zip).

* Type = Polygon shapefile
* Projection: Gauss Kruger Zone 3 (Inchauspe)
* Observations = 209 Electoral Precincts (Circuitos) of the City of Buenos Aires, Argentina
* Variables = 21

**Source**
For further details contact Ernesto Calvo (ecalvo@uh.edu) or Marcelo Escolar (marceloescolar@fibertel.com.ar).

|**Variable** | **Description**|
|---|---|
|INDRA | Indra Code ID|
|PROV | Indec Province Code ID|
|CIRCUNS | Municipality ID|
|CIRC |
|PROVINCIA | Province Name|
|CIRCUNSCRI | Municipality Name|
|CIRCUITO | Precinct ID|
|APR_1 | Total Number of Votes for the Center Right APR "Accion por la Republica"|
|AL_1 | Total Number of Votes for the Centrist "Alianza" (Coalition of UCR and FREPASO)|
|TURNT_1 | Total Number of Effective Voters|
|ELEC_1 | Total Number of Registered Voters|
|VOTPOS_1 | Total Number of Valid Votes|
|AL99CIRC | Percent of Alianza Votes over Valid Votes|
|APR99CIR | Percent of APR Votes over Valid Votes|
|TURN99CR | Percent of Effective Votes over Valid Votes|
|EAST | East Coordinates|
|NORTH | North Coordinates|
I|NDRANO | Numeric ID (for use in GeoDa)|
|APR99PC | Percent of APR Votes over Valid Votes (for use in GeoDa)|
|AL99PC | Percent of Alianza Votes over Valid Votes (for use in GeoDa)|
|TURN99PC | Percent of Effective Votes over Valid Votes (for use in GeoDa)|

Prepared by Luc Anselin.
Last updated June 3, 2004
