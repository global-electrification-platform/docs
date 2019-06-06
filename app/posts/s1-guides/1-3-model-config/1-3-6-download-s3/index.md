---
title: Download from AWS S3
date: 2012-08-23
layout: post.html
---
Models available on GEP website can be downloaded from Amazon S3 using [AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/). Create a folder for the different files using your model id and enter it:

    $ mkdir mw-1 && cd mw-1

The files are stored in a bucket under the following folder structure: `s3://wbg-geography01/GEP/models/<modelId>/explorer/`.

Inside this bucket’s folder there will be one `.zip` file per scenario and a config file `.yml` for the model. To download the needed files run:

    $ aws s3 cp --recursive s3://wbg-geography01/GEP/models/mw-1/explorer/ .

Unzip all `.zip` files to get the scenarios, and then remove the zips to cleanup. Use `unzip \*.zip` and `rm *.zip`