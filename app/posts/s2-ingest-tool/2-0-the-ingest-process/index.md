---
title: The ingest process
date: 2019-01-20
layout: post.html
---

#### Hardware requirements
As models outputs might have gigabytes of data, the ingest process can take several hours to complete, even for small countries. A dedicated computer is needed, with the following requirements:

- Stable network connection
- Sleep/hibernation mode disabled
- 4 GB of RAM or more
- Total free space two times bigger the size of uncompressed scenarios (approx. 250GB for large countries)
- In AWS the minimum instance is `t2.medium`

#### Install the command-line tool
The [gep-data-service](https://github.com/developmentseed/gep-data-service) comes with a CLI (command-line interface) tool to import, delete and update the data in the platform. To install the CLI, clone the repository locally and follow instructions on "Install Dependencies" section. Once done, the CLI the command can be executed at repository root folder with:

    node cli/ [command]

The CLI will need to know the database to which data must be imported. Define a target database by exporting a PostgreSQL connection string to environment variable `PG_CONNECTION_STRING`. Example:

    $ export PG_CONNECTION_STRING=postgresql://user:password@customhost:5432/gep

Please refer to PostgreSQL manual to learn [how to write a connection string](https://www.postgresql.org/docs/9.6/libpq-connect.html#LIBPQ-CONNSTRING).