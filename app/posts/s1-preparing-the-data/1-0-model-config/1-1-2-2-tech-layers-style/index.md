---
title: Tech layers
date: 2012-08-23
layout: post.html
---

Each tech layer configuration object should have the following properties:

- `id`: electrification code;
- `label`: label for the electrification type;
- `color`: color hex code or gep color name to be used on map and legend.

The front-end defines default color values for pre-defined technologies. Although these can be changed, it is not recommended as it may confuse the user. Please refer to [this file](https://github.com/developmentseed/gep-data-service/blob/master/app/tech-layers-config.js) in order to know which colors are available.