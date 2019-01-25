---
title: Vector tiles
date: 2012-09-28
layout: post.html
---

GEP Explorer consumes geo data from vector tilesets in order to render map of scenarios in a efficient way. Every model should have a vector tileset defined in its configuration. At the moment, the GEP Explorer only supports polygon geometries (clusters), not point data.

Each geometry in the dataset should have a single property `id`, of type integer. Other properties should be discarded as they will not be used by the web client and will increase tile size. 

A recommended way to generate and host a vector tileset is to use the command-line tool tippecanoe and upload the resulting MBTiles file to Mapbox Studio. 

An example command to generate MBTiles from GeoJSON:

    tippecanoe -o gep-features.mbtiles gep-features.geojson

The option `--drop-densest-as-needed` should be avoided, if possible, as it limits the number of features displayed on the map at national level, affecting visual analysis.