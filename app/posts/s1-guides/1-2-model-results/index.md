---
title: Formatting Model Results
date: 2012-08-23
layout: post.html
---
Electrification model’s datasets are composed of three parts:


- **Geodata**: geographic features corresponding to each analyzed area;
- **Model configuration**: includes general metadata about the model, like title, description and version. Also includes applicable filters, lever combinations and map display configuration;
- **Scenarios**: series of datasets, each one is the output of a model using a specific lever combination.

Each model is ingested in the platform separately, being composed by one [YAML](https://en.wikipedia.org/wiki/YAML) and several [CSV](https://en.wikipedia.org/wiki/Comma-separated_values) files. The naming convention described below should be followed to allow the CLI tool to identify the model and scenario data correctly:


- `{model_id}.yaml`: model configuration file;
- `{model_id}-{levers_id}.csv`: scenario’s outputs, where `levers_id` is the level combination that generated the results available in each file.