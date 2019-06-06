---
title: Filters
date: 2012-08-23
layout: post.html
---

Each filter object should have the following properties:

- `id`: integer value to set filter order at the interface;
- `key`: property name, as used in scenario file;
- `label`: short string describing the filter;
- `type`: filter type, should be equal to  `range` or `options`. Filtered types should match value types. If type is `range`, scenario values must be numerical, otherwise they should be strings;
- `timestep`: should be equal to `true` or `false`, indicates if the filter can be applied to specific timestep years. If equal to `true`, the timestep years included at model config should in be used to compose property names from scenario files. Example: `FinalElec2023`, `FinalElec2030`. Even if the timestep is `true` the filter `key` should not contain the year.
- `options`: if filter is of `option` type, this property should include an array of objects describing them, with the following properties:
  - `id`: integer option index, used to set options on the interface;
  - `value`: value to query scenario data;
  - `label`: short string describing the option, to display at the interface;