SFCrime\_blocks
---------------
<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the SFCrime_blocks Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../SFCrime_blocks.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>

Data provided "as is", no warranties.

 Incidents of robberies, drugs/narcotics possession or sale, vehicle theft, and vandalism for July 1 to December 31, 2012.
Sources: 2010 Census
 San Francisco Police Department Crime Incident Reporting System

Tags:

 Type = polygon shape file

 Observations = 579

 Variables = 15

 Year = 2010-2012

 Recent

 Spatial resolution = medium

 Topic = crime

 Type of sample data = census/open data

 Rates

|Variable|Description|Source
|---|---|---|
|CENSUSAREA|Area in square miles|2010 Census
|GEO\_displa|Unique census tract identifier|2010 Census
|Population|Population within the area|2010 Census
|Vandalism|Incidents of vandalism in each area|San Francisco Police Department Crime Incident Reporting System
|Robbery|Incidents of robbery in each area|San Francisco Police Department Crime Incident Reporting System
|Drugs|Incidents of drugs in each area|San Francisco Police Department Crime Incident Reporting System
|Car Theft|Incidents of car theft in each area|San Francisco Police Department Crime Incident Reporting System

Updated July 10, 2017
