---
title: "<span style='font-size: 48px'>Developing Data Products - Week 2 Assignment</span>"
author: "<span style='font-size: 24px'>Henry CY Wong</span>"
date: "<span style='font-size: 24px'>2021-04-21</span>"
output: 
    html_document:
            css: style.css
            keep_md: true
---



&nbsp;
&nbsp;

## 1. Introduction

The objective of this assignment is used to create a map with using **Leaflet** in a web page. I would like to use this opportunity to show the location of some sightseeing points in Hong Kong as well.

&nbsp;
&nbsp;

## 2. Build the Map with Leaflet

First of all, let's load the **Leaflet** library.


```r
library(leaflet)
```


Then, the latitudes, longitude sand pop-up texts of Hong Kong sightseeig points are assigned as follows:


```r
mylat <- c(22.312771, 22.246560992402, 22.271121, 22.254106)
mylng <- c(114.041931, 114.1753523356, 114.150233, 113.905144)
mypopup <- c("Disneyland, Hong Kong", "Ocean Park, Hong Kong", "The Peak, Hong Kong", "Tian Tan Buddha, Hong Kong")
mypopularity <- c(1, 4, 10, 7)
```

Finally, the map of Hong Kong sightseeing points are built as below:


```r
mymap <- leaflet() %>%
    addTiles() %>%
    addMarkers(lat = mylat, lng = mylng, popup = mypopup, clusterOptions = markerClusterOptions()) %>%
    addCircleMarkers(lat = mylat, lng = mylng, radius = (sum(mypopularity) - mypopularity) * 2)
mymap
```

<!--html_preserve--><div id="htmlwidget-41525bf622f75f974e8b" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-41525bf622f75f974e8b">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addMarkers","args":[[22.312771,22.246560992402,22.271121,22.254106],[114.041931,114.1753523356,114.150233,113.905144],null,null,null,{"interactive":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},["Disneyland, Hong Kong","Ocean Park, Hong Kong","The Peak, Hong Kong","Tian Tan Buddha, Hong Kong"],null,{"showCoverageOnHover":true,"zoomToBoundsOnClick":true,"spiderfyOnMaxZoom":true,"removeOutsideVisibleBounds":true,"spiderLegPolylineOptions":{"weight":1.5,"color":"#222","opacity":0.5},"freezeAtZoom":false},null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]},{"method":"addCircleMarkers","args":[[22.312771,22.246560992402,22.271121,22.254106],[114.041931,114.1753523356,114.150233,113.905144],[42,36,24,30],null,null,{"interactive":true,"className":"","stroke":true,"color":"#03F","weight":5,"opacity":0.5,"fill":true,"fillColor":"#03F","fillOpacity":0.2},null,null,null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]}],"limits":{"lat":[22.246560992402,22.312771],"lng":[113.905144,114.1753523356]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

&nbsp;
&nbsp;
