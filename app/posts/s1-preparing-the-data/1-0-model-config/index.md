---
title: Model configuration
date: 2012-08-23
layout: post.html
---



A YAML file describes the model configuration and is used to set up the GEP Explorer. It must contain the following properties:


- `id`: unique identifier for model. Can be any string, but [ISO 3166-1 alpha 2 country codes](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) and a integer incremented between versions are recommended. This id and the filename must match;
- `name`: a short string describing model country, type and version;
- `description`: a paragraph describing the model;
- `version`: a string identifying a model version;
- `updatedAt` : date of model creation or update, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601);
- `country`: country code in [ISO 3166-1 alpha 2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format;
- `attribution`: object describing model provider:
  - `author`: name of model provider;
  - `url`: URL to provider website;
- `timesteps`:  an array containing the intermediate and final years used on the model, in respective order;
- `levers`: array of [lever objects]({{baseurl}}/preparing-the-data/levers) describing possible combinations of input variables used on the model. The order of the objects in the array determines the order in the interface.
- `filters`: array of [filter objects]({{baseurl}}/preparing-the-data/filters) describing filters that can be applied to scenario data. The order of the objects in the array determines the order in the interface.
- `map`: describes map configuration to be used at GEP Explorer with the following properties:
  - `modelVT`: 
    - `url`: URL to vector tiles source, according to Mapbox GL JS specification; 
    - `id`: layer name contained by the vector source which has scenarios geometries;
  - `externalLayers`: array of [external layer objects]({{baseurl}}/preparing-the-data/external-layers) describing WMS layers to be offered at contextual layers. The order of the objects in the array determines the order in the interface.
  - `techLayersConfig`: array of [tech layer config objects]({{baseurl}}/preparing-the-data/tech-layers) to override default electrification types used by GEP.
