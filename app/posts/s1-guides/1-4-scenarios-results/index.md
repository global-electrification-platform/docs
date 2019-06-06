---
title: Scenario results
date: 2012-08-23
layout: post.html
---

As each model can have multiple combination of levers, scenarios ids will be composed of model id and a sequence of levers indexes. Let's use an example model for Malawi with 3 levers and the following options:

| Lever                | 0    | 1    | 2     |
| -------------------- | ---- | ---- | ----- |
| grid_generating_cost | 0.05 | 0.08 | 0.010 |
| diesel_price         | 0.5  | 0.8  | 1.0   |
| first_year_target    | 50%  | 70%  |       |
{.table}

This configuration would result in eighteen scenarios, with the following ids:


- mw-1-0_0_0
- mw-1-0_1_0
- mw-1-0_2_0
- mw-1-0_0_1
- mw-1-0_1_1
- mw-1-0_2_1
- mw-1-1_0_0
- mw-1-1_1_0
- mw-1-1_2_0
- mw-1-1_0_1
- mw-1-1_1_1
- mw-1-1_2_1
- mw-1-2_0_0
- mw-1-2_1_0
- mw-1-2_2_0
- mw-1-2_0_1
- mw-1-2_1_1
- mw-1-2_2_1

So, for a scenario of grid_generating_cost of 0.010, diesel_price of 0.5 and first_year_target of 70%, the scenario id would be mw-1-2_0_1.

Each scenario results set should be provided in a single CSV file. The filename should be equal to the scenario id. Each row should include an area identifier (ID), which should match the corresponding feature on the vector tile source, and can include as many other columns. 

The following properties properties are required and should be appended by intermediate and final year if the model has time steps:


- `FinalElecCode`: electrification type code. Should be always defined (null is not accepted). Entries with code of value equal to `99` in intermediate year will be treated as “not electrified”. In final year, code values should be always different of null and `99`;
- `NewCapacity`: Capacity added;
- `InvestmentCost`: Investment needed to electrify the area;
- `Pop`: Population affected.

Scenario data example, for a model with time steps (scroll table to right): 

<div class="scrollable-x">

| ID   | Pop2023     | Pop2030     | FinalElecCode2023 | FinalElecCode2030 | NewCapacity2023 | NewCapacity2030 | InvestmentCost2023 | InvestmentCost2030 | RoadDist | SubstationDist |
| ---- | ----------- | ----------- | ----------------- | ----------------- | --------------- | --------------- | ------------------ | ------------------ | -------- | -------------- |
| 1292 | 29.3781248  | 36.34699214 | 1                 | 1                 | 6.240345872     | 7.720635811     | 798.5822524        | 968.8105636        | 4.2009   | 76.95638       |
| 1293 | 76.23326145 | 94.31676711 | 3                 | 5                 | 6.240649128     | 7.721011003     | 895.6079864        | 1061.419793        | 0.46741  | 77.86368       |
| 1294 | 150.1442365 | 185.7603717 | 99                | 5                 | 6.241472249     | 7.722029379     | 1123.272083        | 2959.004594        | 3.5702   | 77.07007       |
{.table}

</div>
 