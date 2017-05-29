---
layout: post
title: "Baltimore"
date: 2017-05-29 15:26:03
image: '/assets/img/'
description:
main-class: 'HOUSING'
color:
tags:
- point
categories:
twitter_text:
introduction:
---
<script>
var map = L.map('map').setView([39.2904, -76.6122], 12);

	L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);
</script>

House sales price and characteristics for a spatial hedonic regression, Baltimore, MD 1978. Download the file [here](https://s3.amazonaws.com/geoda/data/baltimore.zip).  
Type = point shape file, projected, X,Y on Maryland grid, projection type unknown.  
Observations = 211  
Variables = 17  

**Source**
Original data made available by Robin Dubin, Weatherhead School of Management, Case Western Research University, Cleveland, OH, [Robin.Dubin@weatherhead.cwru.edu](mailto:Robin.Dubin@weatherhead.cwru.edu).  

Reference: Dubin, Robin A. (1992). Spatial autocorrelation and neighborhood quality. Regional Science and Urban Economics 22(3), 433-452.

Variable | Description
---|---
STATION | ID variable
PRICE | sales price of house iin $1,000 (MLS)
NROOM | number of rooms
DWELL | 1 if detached unit, 0 otherwise
NBATH | number of bathrooms
PATIO | 1 if patio, 0 otherwise
FIREPL | 1 if fireplace, 0 otherwise
AC | 1 if air conditioning, 0 otherwise
BMENT | 1 if basement, 0 otherwise
NSTOR | number of stories
GAR | number of car spaces in garage (0 = no garage)
AGE | age of dwelling in years
CITCOU | 1 if dwelling is in Baltimore County, 0 otherwise
LOTSZ | lot size in hundreds of square feet
SQFT | interior living space in hundreds of square feet
X | x coordinate on the Maryland grid
Y | y coordinate on the Maryland grid

Prepared by Luc Anselin  
[UIUC-ACE Spatial Analysis Laboratory](https://anth.uic.edu/uic-anthropology/research-groups/spatial-analysis-laboratory)   
Last updated June 16, 2003
