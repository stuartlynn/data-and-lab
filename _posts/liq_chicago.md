## liq_Chicago

<script>
  var map = L.map('map').setView([28.601151, 84.115914], 6);
  L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', { <!--this is the URL for the liq_chicago Geojson-->
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, ' +
			'<a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="http://mapbox.com">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);

  // load GeoJSON from an external file
  // load GeoJSON from an external file
  $.getJSON("../liq_chicago.geojson",function(data){
    // add GeoJSON layer to the map once the file is loaded
    L.geoJson(data).addTo(map);
  });

</script>

Data provided "as is", no warranties.

Liquor stores in Chicago, IL as of 2015\. Scraped from Google Maps in 2015.

Type = point shape file.

Variables = 2

Observations = 571

Type of sample data = Open data

Year = 2015

Recent

Luc Anselin course lab

Prepared by Center for Spatial Data Science ([https://spatial.uchicago.edu/](https://spatial.uchicago.edu/))
Last updated July 5, 2017.
