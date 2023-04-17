+++
title = "QGIS - Join Shapefile Data to Point Data"
date = "2022-03-23"
author = "JB"
authorTwitter = "" #do not include @
cover = ""
categories = ['GIS']
tags = ["QGIS", "Shapefiles", "Points"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

### Combine Attributes With Shared Geography

Often you will encounter point data (longitude & latitude pairs) that would be more useful with additional geographical boundary context added. In GIS terms, this known as a **spatial join**. An example of this is a list of geocoded points that you want the county or census tract for.  

The points will likely be in a delimited text file (.csv, .txt, etc.) and the geography/boundary data will be polygons in a **[shapefile](https://www.gislounge.com/what-is-a-shapefile/)** (.shp) format.

{{< youtube z3JUBG9urfY >}}