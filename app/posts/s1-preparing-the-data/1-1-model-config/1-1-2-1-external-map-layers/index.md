---
title: External layers
date: 2012-08-23
layout: post.html
---

Each external layer object should have the following properties:

- `id`: short string identifying the layer;
- `label`: layer label to be displayed at the interface;
- `type`: layer type, should be equal to `raster` or `vector`;
- `label`: short string to describe the layers at the interface;
- `url`: URL of tilejson. Only relevant is type is `vector`
- `vectorLayers`: array vector layer ids, if `type` is vector;
- `tiles`: array of tile URLs. Can be used as a mutually exclusive alternative to `url` if type is `vector`. it is required if type is `raster`
- `source`: source for this layer to be displayed on the interface,
  - `label`: label to use;
  - `url`: URL the label points to;