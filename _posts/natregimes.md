---
layout: post
title: "Natregimes"
date: 2017-07-18 16:49:16
image: /assets/img/
description:
main-class: 'CRIME'
color:
tags:
- polygon
- crime
- Research project
- Luc Anselin course lab
- Rates
- Space-time
categories:
twitter_text:
introduction: "Homicides and selected socio-economic characteristics for continental U.S. counties. Data for four decennial census years: 1960, 1970, 1980, 1990."
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the natregimes Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../natregimes.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>


**Data provided "as is," no warranties**


**Description**
---------------

Homicides and selected socio-economic characteristics for continental U.S. counties. Data for four decennial census years: 1960, 1970, 1980, 1990.



Type = polygon shape file, unprojected, lat-lon

Observations = 3085

Variables = 73

Year range = 1959-1990

Spatial resolution = low

Topic = crime

Type of sample data = research project

Rates

Space-time

Luc Anselin course lab

**Source**
----------

S. Messner, L. Anselin, D. Hawkins, G. Deane, S. Tolnay, R. Baller (2000). An Atlas of the Spatial Patterning of County-Level Homicide, 1960-1990. Pittsburgh, PA, [National Consortium on Violence Research (NCOVR)](http://www.ncovr.heinz.cmu.edu/).

Reference: Baller, R., L. Anselin, S. Messner, G. Deane and D. Hawkins (2001). Structural covariates of US county homicide rates: incorporating spatial effects. Criminology 39, 561-590.

**Variables**
-------------

<table>
<col width="50%" />
<col width="50%" />
<tbody>
<tr class="odd">
<td align="left"><p><strong>Variable</strong></p></td>
<td align="left"><p><strong>Description</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>REGIONS</p></td>
<td align="left"><p>regions (South = 0, Midwest/NE = 1, West = 2)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NOSOUTH</p></td>
<td align="left"><p>South region dummy (0 if south)</p></td>
</tr>
<tr class="even">
<td align="left"><p>POLYID</p></td>
<td align="left"><p>unique numeric ID</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NAME</p></td>
<td align="left"><p>county name</p></td>
</tr>
<tr class="even">
<td align="left"><p>STATE_NAME</p></td>
<td align="left"><p>state name</p></td>
</tr>
<tr class="odd">
<td align="left"><p>STATE_FIPS</p></td>
<td align="left"><p>state fips code (character)</p></td>
</tr>
<tr class="even">
<td align="left"><p>CNTY_FIPS</p></td>
<td align="left"><p>county fips code (character)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FIPS</p></td>
<td align="left"><p>combined state and county fips code (character)</p></td>
</tr>
<tr class="even">
<td align="left"><p>STFIPS</p></td>
<td align="left"><p>state fips code (numeric)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>COFIPS</p></td>
<td align="left"><p>county fips code (numeric)</p></td>
</tr>
<tr class="even">
<td align="left"><p>FIPSNO</p></td>
<td align="left"><p>fips code as numeric variable</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SOUTH</p></td>
<td align="left"><p>dummy variable for Southern counties (South = 1)</p></td>
</tr>
<tr class="even">
<td align="left"><p>HR**</p></td>
<td align="left"><p>homicide rate per 100,000 (1960, 1970, 1980, 1990)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HC**</p></td>
<td align="left"><p>homicide count, three year average centered on 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="even">
<td align="left"><p>PO**</p></td>
<td align="left"><p>county population, 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RD**</p></td>
<td align="left"><p>resource deprivation 1960, 1970, 1980, 1990 (principal component, see Codebook for details)</p></td>
</tr>
<tr class="even">
<td align="left"><p>PS**</p></td>
<td align="left"><p>population structure 1960, 1970, 1980, 1990 (principal component, see Codebook for details)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UE**</p></td>
<td align="left"><p>unemployment rate 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="even">
<td align="left"><p>DV**</p></td>
<td align="left"><p>divorce rate 1960, 1970, 1980, 1990 (% males over 14 divorced)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MA**</p></td>
<td align="left"><p>median age 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="even">
<td align="left"><p>POL**</p></td>
<td align="left"><p>log of population 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNL**</p></td>
<td align="left"><p>log of population density 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="even">
<td align="left"><p>MFIL**</p></td>
<td align="left"><p>log of median family income 1959, 1969, 1979, 1989</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FP**</p></td>
<td align="left"><p>% families below poverty 1959, 1969, 1979, 1989 (see Codebook for details)</p></td>
</tr>
<tr class="even">
<td align="left"><p>BLK**</p></td>
<td align="left"><p>% black 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GI**</p></td>
<td align="left"><p>Gini index of family income inequality 1959, 1969, 1979, 1989</p></td>
</tr>
<tr class="even">
<td align="left"><p>FH**</p></td>
<td align="left"><p>% female headed households 1960, 1970, 1980, 1990</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WEST</p></td>
<td align="left"><p>West region dummy (1 if west)</p></td>
</tr>
</tbody>
</table>

Prepared by Center for Spatial Data Science. [https://spatial.uchicago.edu](https://spatial.uchicago.edu)

Last updated January 12, 2017.
