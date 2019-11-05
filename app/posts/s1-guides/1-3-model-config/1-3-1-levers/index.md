---
title: Levers
date: 2012-08-23
layout: post.html
---

Each lever object should have the following properties:

- `id`: lever id, should be integer;
- `label`: short string describing the variable;
- `description`: a paragraph describing the variable;
- `options`: array of objects describing possible values for the lever;
  - `id`: an integer identifying the option, which will be used to sort options at the interface;
  - `value`: value attributed to the option, as an integer or string.