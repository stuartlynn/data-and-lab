---
layout: post
title: "Guerry"
date: 2017-07-18 15:34:43
image: '/assets/img/'
description: "Socioeconomic data for 1830 France, collected by Andre-Michel Guerry."
main-class: 'HISTORICAL'
color:
tags:
- comma separated file
- Demographics
- census data
- Rates
categories:
twitter_text:
introduction: 'Socioeconomic data for 1830 France, collected by Andre-Michel Guerry.'
---
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the Guerry Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../Guerry.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>

Data provided "as is", no warranties.

 Socioeconomic data for 1830 France, collected by Andre-Michel Guerry.
 Data derived from the R package Guerry (Michael Friendly and Stephane Dray). See bottom of page for details on sources. 

Tags:

 Type = comma separated file

 Observations = 85

 Variables = 23

 Year = 1815-1834

 Spatial resolution = low

 Topic = Demographics

 Type of sample data = census

 Rates

<table>
<col width="33%" />
<col width="33%" />
<col width="33%" />
<tbody>
<tr class="odd">
<td align="left"><p><strong>Variable</strong></p></td>
<td align="left"><p><strong>Description</strong></p></td>
<td align="left"><p><strong>Source</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>dept, code_de</p></td>
<td align="left"><p>Department ID: Standard numbers for the departments</p></td>
<td align="left"><p><br /></p></td>
</tr>
<tr class="odd">
<td align="left"><p>region</p></td>
<td align="left"><p>Region of France ('N'='North', 'S'='South', 'E'='East', 'W'='West', 'C'='Central')</p></td>
<td align="left"><p><br /></p></td>
</tr>
<tr class="even">
<td align="left"><p>dprtmnt</p></td>
<td align="left"><p>Department name: Departments are named according to usage in 1830, but without accents. </p>
<p>A factor with levels Ain Aisne Allier ... Vosges Yonne</p></td>
<td align="left"><p><br /></p></td>
</tr>
<tr class="odd">
<td align="left"><p>crm_prs</p></td>
<td align="left"><p>Population per Crime against persons.</p></td>
<td align="left"><p>A2 (Compte général, 1825-1830)</p></td>
</tr>
<tr class="even">
<td align="left"><p>crm_prp</p></td>
<td align="left"><p>Population per Crime against property.</p></td>
<td align="left"><p>A2 (Compte général, 1825-1830)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>litercy</p></td>
<td align="left"><p>Percent of military conscripts who can read and write.</p></td>
<td align="left"><p>A2 </p></td>
</tr>
<tr class="even">
<td align="left"><p>donatns</p></td>
<td align="left"><p>Donations to the poor.</p></td>
<td align="left"><p>A2 (Bulletin des lois)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>infants</p></td>
<td align="left"><p>Population per illegitimate birth.</p></td>
<td align="left"><p>A2 (Bureau des Longitudes, 1817-1821)</p></td>
</tr>
<tr class="even">
<td align="left"><p>suicids</p></td>
<td align="left"><p>Population per suicide.</p></td>
<td align="left"><p>A2 (Compte général, 1827-1830)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>maincty</p></td>
<td align="left"><p>Size of principal city ('1:Sm', '2:Med', '3:Lg'), used as a surrogate for population density. Large refers to the top 10, small to the bottom 10; all the rest are classed Medium.</p></td>
<td align="left"><p>A1. An ordered factor with levels</p></td>
</tr>
<tr class="even">
<td align="left"><p>wealth</p></td>
<td align="left"><p>Per capita tax on personal property. A ranked index based on taxes on personal and movable property per inhabitant.</p></td>
<td align="left"><p>A1</p></td>
</tr>
<tr class="odd">
<td align="left"><p>commerc</p></td>
<td align="left"><p>Commerce and Industry, measured by the rank of the number of patents / population.</p></td>
<td align="left"><p>A1</p></td>
</tr>
<tr class="even">
<td align="left"><p>clergy</p></td>
<td align="left"><p>Distribution of clergy, measured by the rank of the number of Catholic priests in active service / population.</p></td>
<td align="left"><p>A1 (Almanach officiel du clergy, 1829)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>crim_prn</p></td>
<td align="left"><p>Crimes against parents, measured by the rank of the ratio of crimes against parents to all crimes – Average for the years 1825-1830.</p></td>
<td align="left"><p>A1 (Compte général)</p></td>
</tr>
<tr class="even">
<td align="left"><p>infntcd</p></td>
<td align="left"><p>Infanticides per capita. A ranked ratio of number of infanticides to population – Average for the years 1825-1830.</p></td>
<td align="left"><p>A1 (Compte général)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>dntn_cl</p></td>
<td align="left"><p>Donations to the clergy. A ranked ratio of the number of bequests and donations inter vivios to population – Average for the years 1815-1824.</p></td>
<td align="left"><p>Source: A1 (Bull. des lois, ordunn. d'autorisation)</p></td>
</tr>
<tr class="even">
<td align="left"><p>lottery</p></td>
<td align="left"><p>Per capita wager on Royal Lottery. Ranked ratio of the proceeds bet on the royal lottery to population — Average for the years 1822-1826.</p></td>
<td align="left"><p>A1 (Compte rendu par le ministre des finances)</p></td>
</tr>
<tr class="odd">
<td align="left">desertn</td>
<td align="left"><p>Military desertion, ratio of the number of young soldiers accused of desertion to the force of the military contingent, minus the deficit produced by the insufficiency of available billets – Average of the years 1825-1827.</p></td>
<td align="left"><p>A1 (Compte du ministère du guerre, 1829 état V)</p></td>
</tr>
<tr class="even">
<td align="left"><p>instrct</p></td>
<td align="left"><p>Instruction. Ranks recorded from Guerry's map of Instruction. Note: this is inversely related to Literacy (as defined here)</p></td>
<td align="left"><p><br /></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Prsttts</p></td>
<td align="left"><p></p>
<p>Number of prostitutes registered in Paris from 1816 to 1834, classified by the department of their birth</p></td>
<td align="left"><p>Source: Parent-Duchatelet (1836), <em>De la prostitution en Paris</em></p></td>
</tr>
<tr class="even">
<td align="left"><p>distanc</p></td>
<td align="left"><p>Distance to Paris (km). Distance of each department centroid to the centroid of the Seine (Paris)</p></td>
<td align="left"><p>Source: calculated from department centroids</p></td>
</tr>
<tr class="odd">
<td align="left"><p>area</p></td>
<td align="left"><p>Area (1000 km^2).</p></td>
<td align="left"><p>Angeville (1836)</p></td>
</tr>
<tr class="even">
<td align="left"><p>pop1831</p></td>
<td align="left"><p>Population in 1831, in 1000s</p></td>
<td align="left"><p>taken from Angeville (1836), <em>Essai sur la Statistique de la Population français</em></p></td>
</tr>
</tbody>
</table>

Prepared by Center for Spatial Data Science. Last updated July 3, 2017.

### **Details**

Note that most of the variables (e.g., Crime\_pers) are scaled so that more is “better”. 

Values for the quantitative variables displayed on Guerry's maps were taken from Table A2 in the English translation of Guerry (1833) by Whitt and Reinking. Values for the ranked variables were taken from Table A1, with some corrections applied. The maximum is indicated by rank 1, and the minimum by rank 86. 

### **Sources**

Angeville, A. (1836). *Essai sur la Statistique de la Population française* Paris: F. Doufour. 

Guerry, A.-M. (1833). *Essai sur la statistique morale de la France* Paris: Crochard. English translation: Hugh P. Whitt and Victor W. Reinking, Lewiston, N.Y. : Edwin Mellen Press, 2002. 

Parent-Duchatelet, A. (1836). *De la prostitution dans la ville de Paris*, 3rd ed, 1857, p. 32, 36 

### **References**

Dray, S. and Jombart, T. (2011). A Revisit Of Guerry's Data: Introducing Spatial Constraints In Multivariate Analysis. *The Annals of Applied Statistics*, Vol. 5, No. 4, 2278-2299. [http://arxiv.org/pdf/1202.6485.pdf](http://arxiv.org/pdf/1202.6485.pdf), DOI: 10.1214/10-AOAS356. 

Brunsdon, C. and Dykes, J. (2007). Geographically weighted visualization: interactive graphics for scale-varying exploratory analysis. Geographical Information Science Research Conference (GISRUK 07), NUI Maynooth, Ireland, April, 2007. 

Friendly, M. (2007). A.-M. Guerry's Moral Statistics of France: Challenges for Multivariable Spatial Analysis. *Statistical Science*, 22, 368-399. 

Friendly, M. (2007). Data from A.-M. Guerry, Essay on the Moral Statistics of France (1833), [http://datavis.ca/gallery/guerry/guerrydat.html](http://datavis.ca/gallery/guerry/guerrydat.html). 

### **See Also**

The Guerry package for maps of France: gfrance and related data. 
