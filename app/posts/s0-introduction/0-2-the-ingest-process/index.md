---
title: The ingest process
date: 2019-01-20
layout: post.html
---

New models can be added to the Global Electrification Platform via command line interface using an specialized tool helps validate and ingest data to the production database.

All models to be imported need to be formatted following the specification at "Prepare the data" section.

Each model is ingested in the platform separately, as a set of files in [YAML](https://en.wikipedia.org/wiki/YAML) and [CSV](https://en.wikipedia.org/wiki/Comma-separated_values) formats. The following naming convention should be followed to allow the CLI tool identify the model and scenario data correctly:


- `{model_id}.yaml`: model configuration file;
- `{model_id}-{levers_id}.csv`: scenarios outputs, where `levers_id` is the level combination that generated the results available in a file.