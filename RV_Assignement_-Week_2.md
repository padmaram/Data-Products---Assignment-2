# DevelopingDataProducts - Assignment 2
## Summary Instructions
## Date: 5/21/2017

Create a web page using R Markdown that features a map created with Leaflet.

Host your webpage on either GitHub Pages, RPubs, or NeoCities.

Your webpage must contain the date that you created the document, and it must contain a map created with Leaflet. We would love to see you show off your creativity!
Review criteria

The rubric contains the following two questions:

1. Does the web page feature a date and is this date less than two months before the date that you're grading        this assignment?
2. Does the web page feature an interactive map that appears to have been created with Leaflet?

## Submission: 

## Temples of Kumbakonam, South India




```r
library(leaflet)
```

```
## Warning: package 'leaflet' was built under R version 3.3.3
```

```r
df <- read.csv2("./data/kumbakonam.csv", header=TRUE, dec=".", sep = ",")
head(df)
```

```
##                       temple     Lat    Long
## 1 Sri Adi Kumbeswarar Temple 10.9583 79.3711
## 2         Sarangapani Temple 10.9595 79.3750
## 3     Nageswara Swami Temple 10.9587 79.3787
## 4     Sri Uppiliappan Temple 10.9616 79.4316
```


```r
my_map <- leaflet() %>% 
  addTiles() %>% 
  addMarkers(lat=10.9617, lng=79.3881, popup = "Beautiful Temples of Kumbakonam, South India") %>%
  addTiles() %>%
  addMarkers(lat=as.numeric(df$Lat), lng = as.numeric(df$Long), popup = df$temple)
my_map
```

<!--html_preserve--><div id="htmlwidget-c99b9a7407801b538a79" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-c99b9a7407801b538a79">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"maxNativeZoom":null,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"continuousWorld":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":null,"unloadInvisibleTiles":null,"updateWhenIdle":null,"detectRetina":false,"reuseTiles":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap\u003c/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA\u003c/a>"}]},{"method":"addMarkers","args":[10.9617,79.3881,null,null,null,{"clickable":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},"Beautiful Temples of Kumbakonam, South India",null,null,null,null,null,null]},{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"maxNativeZoom":null,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"continuousWorld":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":null,"unloadInvisibleTiles":null,"updateWhenIdle":null,"detectRetina":false,"reuseTiles":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap\u003c/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA\u003c/a>"}]},{"method":"addMarkers","args":[[10.9583,10.9595,10.9587,10.9616],[79.3711,79.375,79.3787,79.4316],null,null,null,{"clickable":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},["Sri Adi Kumbeswarar Temple","Sarangapani Temple","Nageswara Swami Temple","Sri Uppiliappan Temple"],null,null,null,null,null,null]}],"limits":{"lat":[10.9583,10.9617],"lng":[79.3711,79.4316]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->
