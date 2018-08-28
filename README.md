# Docker Compose File for CouchDB and Lucene

For the [Preference Terms Dictionary](http://terms.raisingthefloor.org/) and [Unified Listing API](http://api.ul.gpii.net/), we use
[CouchDB](http://couchdb.apache.org) to store our data and [couchdb-lucene](https://github.com/rnewson/couchdb-lucene) to search the data.

This package provides a sample [configuration file](https://docs.docker.com/compose/compose-file) that can be used to to spin up both
using [Docker Compose](https://docs.docker.com/compose/).

It uses [the official CouchDB Docker image](https://github.com/apache/couchdb-docker) and [a contributed couchdb-lucene image](https://github.com/klaemo/docker-couchdb-lucene).
This minimum configuration exposes the CouchDB instance to the couchdb-lucene instance, which expects for that to be aliased as "couchdb".

Note: The PTD and UL make direct calls to couchdb-lucene.  If you are making use of the proxy integration between couchdb-lucene and CouchDB, check
out the [example provided here](https://github.com/klaemo/docker-couchdb-lucene/tree/master/example).

## Requirements

1. Docker.
2. Docker Compose (generally included on platforms like OS X).
3. An internet connection to download the required Docker images.

## Usage

To start a multi-container environment using this configuration, use a command like `docker-compose up -d` from the root of this repository.
