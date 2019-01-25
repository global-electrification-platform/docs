---
title: Example file
date: 2012-08-23
layout: post.html
---

An example of model configuration file:


    id: mw-1
    name: Malawi OnSSET v1.0
    updatedAt: 2018-10-12
    version: v1.0
    type: onsset
    country: MW
    timesteps:
      - 2023
      - 2030
    attribution:
      author: KTH
      url: http:/kth.se
    description: Magna et commodo minim id pariatur non voluptate mollit sit sit culpa eu ut cupidatat. Officia aliquip nisi dolor velit.
      - id: 0
        label: Grid Generation Cost
        description: Laboris velit cupidatat aliquip nisi consectetur deserunt tempor nisi magna. Reprehenderit tempor voluptate amet dolore aute anim qui aute est.
        options:
          - id: 0
            value: 0.01
          - id: 1
            value: 0.05
          - id: 2
            value: 0.08
      - id: 1
        label: Diesel Price
        description: Cupidatat non cillum Lorem officia cupidatat. Deserunt et incididunt in incididunt excepteur dolor fugiat do.
        options:
          - id: 0
            value: 0.50
          - id: 1
            value: 0.80
          - id: 2
            value: 1.00
      - id: 2
        label: First Year Target
        description: Tempor culpa sit occaecat minim sint esse eu. Aliqua officia ullamco non consequat.
        options:
          - id: 0
            value: 50%
          - id: 1
            value: 70%
    filters:
      - id: 0
        key: Pop
        label: Area Population
        timestep: false
        type: range
      - id: 1
        key: GridCellArea
        label: Area Size (square km)
        timestep: false
        type: range
      - id: 2
        key: FinalElecCode
        label: Electrification Techonology
        timestep: true
        type: options
        options:
          - id: 0
            value: 1
            label: Grid extension
          - id: 1
            value: 2
            label: Stand-alone - Diesel
          - id: 2
            value: 3
            label: Stand-alone - Photovoltaic
          - id: 3
            value: 4
            label: Mini-grid - Diesel
          - id: 4
            value: 5
            label: Mini-grid - Photovoltaic
          - id: 5
            value: 6
            label: Mini-grid - Wind
          - id: 6
            value: 7
            label: Mini-grid - Hydro
      - id: 3
        key: SubstationDist
        label: Distance from existing grid (km)
        timestep: false
        type: range
      - id: 4
        key: RoadDist
        label: Distance from existing road network (km)
        timestep: false
        type: range
      - id: 5
        key: InfrastructureCapitaCost2030
        label: Investiment Cost Per Capita (USD)
        type: range
    map:
      modelVT:
        url: mapbox://devseed.2a5bvzlz
        id: mw
      externalLayers:
        - id: mapbox_satellite
          label: Mapbox Satellite     
          type: raster
          tiles:
            - https://a.tiles.mapbox.com/v4/mapbox.satellite/{z}/{x}/{y}@2x.jpg?access_token=pk.eyJ1IjoiZGV2c2VlZCIsImEiOiJjam9vamtjc2ExaHl2M3FxYW0yeTNjeHprIn0.EGNe0UbYK1gEQSB9Bs9YYw
        - id: wind-potential
          label: Wind Potential (2015)
          type: vector
          url: https://energydata-tiles-bk.s3.amazonaws.com/tiles/faaec345-c386-4cd7-832f-e70443fd2fa2-77d89202-a356-4dee-86c2-c9e2880fab46/data.tilejson
          source:
            label: energydata.info
            url: https://energydata.info
          vectorLayers:
            - data_layer
        - id: africa
          label: Africa Electricity Grid
          type: vector
          url: https://energydata-tiles-bk.s3.amazonaws.com/tiles/19f22355-d631-4b25-a3a3-7a2bfe776720-137f3be9-3cb5-49d0-8d02-5f266f4ce455/data.tilejson
          source:
            label: energydata.info
            url: https://energydata.info
          vectorLayers:
            - data_layer
        - id: healthsites
          label: Malawi Healthsites
          type: vector
          tiles:
            - https://data.humdata.org/gis/services/postgis/pre_c2970f98_f65f_4a11_b717_c8018dffc94f/wkb_geometry/vector-tiles/{z}/{x}/{y}.pbf
          source:
            label: Global Healthsites Mapping Project
            url: https://data.humdata.org/dataset/malawi-healthsites
          vectorLayers:
            - PROJ_LIB
      techLayersConfig:
        - id: 10
          label: New energy
          color: #fff
