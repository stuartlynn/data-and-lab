---
layout: dataset             # don't change this
name: "communitypop"               # one-word reference name for dataset, all lowercase and underscores, e.g. "columbus"
title: "Chicago Community Area Population 2010"              # title of dataset, e.g "Columbus Crime 1980"
introduction: "Population data for 77 community areas in Chicago, IL, 2010"       # one-sentence description of dataset, e.g. "Crime and neighborhood data for 49 neighborhoods in Columbus, OH, 1980."
description: "Population data for 77 community areas in Chicago, IL, 2010. Non-spatial file. Used in Spatial Data Handling tutorial in documentation"        # multiple-sentence description of dataset, e.g. "Crime, housing and income data for 49 neighborhoods in Columbus, OH, 1980. Textbook example."
download_link: "https://geoda.s3.amazonaws.com/data/Community_Pop.zip"      # URL of link to download dataset, e.g. "../data/columbus.zip"

observations: 77         # a number, e.g. 49; a boxed, comma-separated list if multiple datasets, e.g. [49, 100]
variables: 2            # a number, e.g. 20; a boxed, comma-separated list if multiple datasets, e.g. [20, 25]
start_date: 2010-01-01          # date in yyyy/mm/dd of start of data, e.g. 1980-01-01
end_date: 2010-01-01            # date in yyyy/mm/dd of end of data, e.g. 1980-01-01, same as above if single period
spatial_structure: "NA"  # most often, "Point" or "Polygon"
spatial_unit: "Community area"       # short description of the smallest spatial unit, e.g. "City neighborhood", "Census block", "House sale"

source: [""]           # boxed, comma-separated list of citation(s) of publication(s) from which this dataset originates, e.g. ["Anselin, Luc (1988). Spatial Econometrics. Boston, Kluwer Academic, Table 12.1, p. 189.", ""]
reference: [""]        # boxed, comma-separated list of citations(s) of publication(s) that reference this dataset

csv_name: "communitypop"           # the name of the csv with the data dictionary (without the .csv extension), e.g. "columbus"; this csv is stored in the _data folder
prepared_by: "Luc Anselin"        # the name of the person or organization who prepared the data, e.g. "CSDS", "Luc Anselin"
updated: 2010-02-11              # date in yyyy/mm/dd of last updated date, e.g. 2003-06-16
license: "Data provided “as is,” no warranties."            # license/disclaimers for the data, e.g. "Data provided “as is,” no warranties."

used_in: ["GeoDa Documentation"]          # boxed, comma-separated list of CSDS resources using this dataset, e.g. ["GeoDa Sample Data", "Introduction to Spatial Data Science labs"]
use_case: "Spatial data handling"           # short description of use case for dataset, e.g. "Spatial hedonic regression"
main-class: "population"         # Main tag for dataset, e.g. "crime". Will show up on website under this category
tags: ["non-spatial", "textbook", "<500"]    # Secondary tags for data, including the main tag, e.g. ["crime", "polygons", "<500", "smaller areas", "ESDA", "textbook"].
---

{% comment %}
Please do not edit any of the following code, which creates a templated dataset
documentation webpage from the above information block. You should change only 
the parts that are labeled FIXME.
{% endcomment %}

<span class="download">[DOWNLOAD DATA]({{ page.download_link }})</span>

<p class="description">{{ page.description }}</p>

* Observations = <span class="observations">{{ page.observations }}</span>

* Variables = <span class="variables">{{ page.variables }}</span>

{% if page.start_date == page.end_date %}
* Date = <span class="start_date">{{ page.start_date }} </span>
{% elsif page.start_date != page.end_date %}
* Date Range = <span class="start_date">{{ page.start_date }}</span> to <span class="end_date">{{ page.end_date }}</span>
{% endif %}

{% if page.source %}
**Source**
<p class="source">{{ page.source }}</p>
{% endif %}

{% if page.reference %}
**Reference**
<p class="reference">{{ page.reference }}</p>
{% endif %}

<table class="datadict">
  <thead>
    <tr>
      <th style="text-align: left">Variable</th>
      <th style="text-align: left">Description</th>
    </tr>
  </thead>
  <tbody>
{% for var in site.data[page.csv_name] %}
    <tr>
      <td class="var" style="text-align: left">{{ var.Variable }}</td>
      <td class ="desc" style="text-align: left">{{ var.Description }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>

Prepared by <span class="prepared">{{ page.prepared_by }}</span>. Last updated <span class="updated">{{ page.updated }}</span>. <span class="license">{{ page.license }}</span>
