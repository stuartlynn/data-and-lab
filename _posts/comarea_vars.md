---
layout: post
title: "Community areas"
date: 2017-07-18 16:50:16
image: /assets/img/
description:
main-class: 'HEALTH'
color:
tags:
- polygon
- health
- census/open data
- Luc Anselin course lab
- Rates
- Space-time
categories:
twitter_text:
introduction: "Public health indicators for the 77 community areas of Chicago, IL, 2014."
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the ComArea_ACS14_f Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../ComArea_ACS14_f.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>

Data provided "as is", no warranties.

Public health indicators for the 77 community areas of Chicago, IL, 2014.


 Type = polygon shape file.

 Variables = 86

 Observations = 77

 Year range = 2012-2014

 Spatial resolution = medium

 Topic = health

 Type of sample data = Census/Open data

 Rates

 Space-time

 Luc Anselin course lab

|Variable name|Description|Source
|--
|Pop2012|Population in 2012|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pop2014|Population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PopM|Male Population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PopF|Female population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Under5|Population age 0-5 in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Under18|Population age 0-18 in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Over21|Population over age 21 in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Over65|Population over age 65 in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Wht14|White population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Blk14|Black population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|AI14|American Indian population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|AS14|Asian population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|NHP14|Native Hawaiian population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Oth14|Population of other races in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Hisp14|Hispanic population in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PopMP, PopFP, Under5P, Under18P, Over18P, Over21P, Over65P, Wht14P, Blk14P, AI14P, AS14P, NHP14P, Oth14P, Hisp14P|Proportion of each corresponding group in the overall population (2014)|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Property\_C|Number of property crimes|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PropCrRt|Property crime rate in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Violent\_C|Number of violent crimes|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|VlntCrRt|Violent crime rate in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PerCInc14|Per Capita Income|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|PPop14|2014 Population base for 2014 poverty counts|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov14|Number of people living in poverty in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|ChildPov14|Number of children (age 0-18) living in poverty in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|NoHS14|Number of adults without a high school diploma in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|HSGrad14|Number of high school graduates in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|SmClg14|Number of people who have some college education in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|ClgGrad14|Number of people who have a college degree in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|LaborFrc|Number of people in the labor force in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Unemp14|Number of people unemployed in 2014|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov50|Number of people with income below 50% of the poverty line|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov125|Number of people with income below 125% of the poverty line|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov150|Number of people with income below 150% of the poverty line|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov185|Number of people with income below 185% of the poverty line|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov200|Number of people with income below 200% of the poverty line|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|Pov50P . . . Pov200P|Proportion of each group in overall population (different poverty rates, 2014)|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|SESave|Average SES|[American Community Survey, US Census Bureau, 2014](http://www.cmap.illinois.gov/data/metropulse/community-snapshots)
|COIave|Average Childhood Opportunity Index|Chicago Dept of Public Health, Childhood Opportunity Index
|HISave|Average Economic Hardship Index|Based on ACS 2014 data; methods: Intercity Hardship Index by Nathan and Adams
|Hlitave|Average health literacy|Health Literacy Project
|Birthrate|Birth rate per 1000 residents|Public Health Statistics- Selected public health indicators by Chicago community area. [City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|FertRate|Fertility rate per 1000 females aged 15-44|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|LowBirthR|Percent of live births with low birth weight|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|PrenScrn|Percent of females delivering a live birth, in which prenatal care began in first trimester|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|PretBrth|Preterm births as percent of live births|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|TeenBirth|Teen birth rate per 1000 females aged 15-19|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|Assault|Homicide deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|BrstCancr|Breast cancer deaths per 100,000 females (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|CancerAll|Cancer deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|Colorect|Colorectal cancer deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|DiabetM|Diabetes-related deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|FirearmM|Firearm-related deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|InfntMR|Infant mortality rate: deaths per 1000 live births|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|LungCancer|Lung cancer deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|ProstateC|Prostate cancer deaths per 100,000 males (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|Stroke|Stroke deaths per 100,000 persons (age adjusted)|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|ChlBLLS|Childhood blood lead level screening, per 1000 children aged 0-6 years|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|ChlLeadP|Childhood lead poisoning per 100|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|GonorrF|Gonorrhea in females, per 10,000 females age 15-44|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|GonorrM|Gonorrhea in males, per 10,000 females age 15-44|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)
|Tuberc|Tuberculosis per 100,000 persons|[City of Chicago Data Portal](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu)

Economic Hardship Index method based on the Intercity Hardship Index, by Richard P. Nathan and Charles F. Adams, Jr. in *Understanding Urban Hardship*, Political Science Quarterly 91 (Spring 1976): 47-62.)

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))
 Last updated July 6, 2017.
