---
title: Available commands
date: 2019-01-20
layout: post.html
---

The [gep-data-service](https://github.com/developmentseed/gep-data-service) comes with a CLI (command-line interface) tool to import, delete and update the data in the platform.
To install the CLI, clone the repository locally and follow instructions on "Install Dependencies" section. Once done, the CLI the command can be executed at repository root folder with:


    node cli/ [command]

The CLI will interact with the database through a connection string defined through the `PG_CONNECTION_STRING` environment variable.


    export PG_CONNECTION_STRING=<connection-string>

## list
Outputs the existing models in the database. Example:


    node cli/ list

## delete <ids…>
Deletes the models and respective data that match the given ids. Example:


    node cli/ delete mw-1 mw-2

## validate <path>
Validates the model and data at the given `path`. The path should point to the directory where the model and data are stored, not to the model itself. Example:

    node cli/ validate ./data/mw-1/

## ingest [options] <path>
Ingests the model and data at the given `path`. The path should point to the directory where the model and data are stored, not to the model itself. Example:


    node cli/ ingest ./data/mw-1/

If there is a model with the same id in the database the command will fail. If you want to re-ingest the model and override the existent one use the `--override` flag. Example:


    node cli/ ingest --override ./data/mw-1/

## ingest --config-only <path>

Updates the non-data parts of model found at the given `path`. The path should point to the directory where the model and data are stored, not to the model itself.

While it is not possible to update data related configurations (like levers and filters) without performing a full ingest, it is allowed to update metadata information, like descriptions and labels. Example:


    node cli/ ingest --config-only ./data/mw-1/

The following model properties can only be modified when doing a full ingest and the script will error if they’re changed:


    id
    country
    timesteps
    levers (for each lever object)
      id
      options (for each option object)
        id
        value
    filters (for each filter object)
      id
      key
      type
      timestep
      options (for each option object)
        id
        value
