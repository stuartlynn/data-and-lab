---
layout: post
title: "US County Health, Income and Diversity (2000)"
date: 2017-07-18 16:44:16
image: /assets/img/
description:
main-class: 'health'
color:
tags:
- polygons
- 500 - 5,000
- larger areas
- ESDA
- Census
- open data
categories:
twitter_text:
introduction: "2000 US county health, income and diversity data."
---
<script>
  var map = L.map('map');
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the income_diversity Geojson-->
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
  $.getJSON("../data/income_diversity.geojson",function(data){
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

 Income, race, and public health statistics for US counties.
 Sources:
 [philpierdo2](https://philpierdo2.carto.com/me)
 [Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
 [Chetty, Stepner, Abraham, Lin, Scuderi, Turner, Bergeron, and Cutler (2016). The Association Between Income and Life Expectancy in the United States, 2001-2014. Health Statistics by County.](http://www.equality-of-opportunity.org/data/)


* Observations = 3,984
* Variables = 75
* Year = 2000


|Variable|Description|Source
|---|---|---|
|ratio|The county's median income divided by the state's median income|[https://philpierdo2.carto.com/me](https://philpierdo2.carto.com/me)
|cty\_pop200|County's population in 2000|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q1\_|Female life expectancy, 1st Income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_raceadj|Female life expectancy, 1st Income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q2|Female life expectancy, 2nd Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_1|Female life expectancy, 2nd Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q3|Female life expectancy, 3rd Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_2|Female life expectancy, 3rd Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q4|Female life expectancy, 4th Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_3|Female life expectancy, 4th Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q11|Male life expectancy, 1st Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_4|Male life expectancy, 1st Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q21|Male life expectancy, 2nd Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_5|Male life expectancy, 2nd Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q31|Male life expectancy, 3rd Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_6|Male life expectancy, 3rd Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_agg\_q41|Male life expectancy, 4th Income Quartile, not adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|le\_racea\_7|Male life expectancy, 4th Income Quartile, adjusted for race|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_agg\_|Standard error for female life expectancy, 1st income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_race|Standard error for female life expectancy, 1st income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_agg1|Standard error for female life expectancy, 2nd income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_1|Standard error for female life expectancy, 2nd income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_1|Standard error for female life expectancy, 3rd income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_2|Standard error for female life expectancy, 3rd income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_2|Standard error for female life expectancy, 4th income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_3|Standard error for female life expectancy, 4th income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_3|Standard error for male life expectancy, 1st income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_4|Standard error for male life expectancy, 1st income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_4|Standard error for male life expectancy, 2nd income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_5|Standard error for male life expectancy, 2nd income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_5|Standard error for male life expectancy, 3rd income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_6|Standard error for male life expectancy, 3rd income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ag\_6|Standard error for male life expectancy, 4th income Quartile, not adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|sd\_le\_ra\_7|Standard error for male life expectancy, 4th income Quartile, adjusted for race.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q1\_F|Female count, 1st income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q2\_F|Female count, 2nd income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q3\_F|Female count, 3rd income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q4\_F|Female count, 4th income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q1\_M|Male count, 1st income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q2\_M|Male count, 2nd income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q3\_M|Male count, 3rd income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|count\_q4\_M|Male count, 4th income quartile.|[Chetty et al. 2016](http://www.equality-of-opportunity.org/data/)
|Diversity-|Diversity Index|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
|Asian alon|Asian alone, percent|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
|Native Haw|Native Hawaiian, percent|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
|Two or Mor|Two or more races, percent|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
|Hispanic o|Hispanic, percent|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)
|White alon|White alone, percent|[Kaggle](https://www.kaggle.com/mikejohnsonjr/us-counties-diversity-index)|

Prepared by Manoradhan Murugesan.

Updated July 10, 2017
