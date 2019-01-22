---
title: Model configuration
date: 2012-08-23
layout: post.html
---

Each model is ingested in the platform separately. The set of files should follow a name convention and be stored in a directory. Each directory should only contain a single model and its data.


- `{model_id}.yaml`: Describes model metadata and how it should be displayed at GEP Explorer; 
- `{model_id}-{levers_set_id}.csv`: Files containing scenario results for a specific lever combination.

A YAML file describes the model configuration and is used to set up the GEP Explorer. It must contain the following properties:


- `id`: unique identifier for model. It can be any string, but a country code (ISO 3166-1 alpha 2) and a integer is recommended. This id and the filename must match.
- `name`: a short string describing model country, model type and version;
- `description`: a paragraph describing the model;
- `version`: a string identifying a model version;
- `updatedAt` : date of model creation or update, in ISO 8601 format;
- `country`: country identifier following ISO 3166-1 alpha 2 format;
- `attribution`: identification of the organization that provided the model;
  - `author`: Name of the organization;
  - `url`: URL to the relevant website;
- `timesteps`:  an array containing the intermediate and final years used on the model, in respective order;
- `levers`: array of lever objects describing possible combinations of input variables used on the model. The order of the objects in the array determines the order in the interface.
- `filters`: array of filter objects describing filters that can be applied to scenario data. The order of the objects in the array determines the order in the interface.
- `map`: describes map configuration to be used at GEP Explorer with the following properties:
  - `modelVT`: 
    - `url`: URL to vector tiles source, according to Mapbox GL JS specification; 
    - `id`: layer name contained by the vector source which has scenarios geometries;
  - `externalLayers`: array of external layer objects describing WMS layers to be offered at contextual layers. The order of the objects in the array determines the order in the interface.
  - `techLayersConfig`: array of tech layer config objects to override default electrification types used by GEP.
