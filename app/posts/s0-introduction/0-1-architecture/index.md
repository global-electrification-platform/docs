---
title: Architecture overview
date: 2019-01-20
layout: post.html
---

The components of GEP:

- **Explorer**: a[single-page application](https://en.wikipedia.org/wiki/Single-page_application) to visualize electrification scenarios via web browser;
- **Data Service**: [a server-side web API](https://en.wikipedia.org/wiki/Web_API) used by the Explorer to query scenarios data;
- **Relational database**: PostgreSQL instance that store scenarios results and visualization options;
- **Map service**: [vector tile server](https://en.wikipedia.org/wiki/Vector_tiles) used by the Explorer to fetch geospatial data for styling the maps;