---
title: Levers
date: 2012-08-23
layout: post.html
---

Each lever object should have the following properties:

- `id`: Id of the lever. Recommended to be an integer.
- `label`: short string identifying the variable;
- `description`: a paragraph describing the variable;
- `options`: array of objects describing possible values for the lever;
  - `id`: an integer identifying the option, which will be used to sort options at the interface;
  - `value`: value attributed to the option, as an integer or string;