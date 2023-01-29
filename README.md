# rte-influxdb
Influx database to store RTE Data from ETL

* [InfluxDB](https://github.com/influxdata/influxdb) - time series database

## Quick Start

To start the app:

1. Install [docker-compose](https://docs.docker.com/compose/install/) on the docker host.
2. Clone this repo on the docker host.
3. Optionally, change default credentials.
4. Run the following command from the root of the cloned repo:
```
docker-compose up -d
```

To stop the app:

1. Run the following command from the root of the cloned repo:
```
docker-compose down
```

## Ports

The services in the app run on the following ports:

| Host Port | Service |
| - | - |
| 8086 | InfluxDB |


If docker is running on a remote machine that supports SSH, use the following command to setup an SSH tunnel to securely access Chronograf by forwarding port 8888 on the remote machine to port 8888 on the local machine:

```
ssh [options] <user>@<docker-host> -L 8888:localhost:8888 -N
```

## Volumes

The app creates the following named volumes (one for each service) so data is not lost when the app is stopped:

* influxdb-storage

## Users

The app creates one admin user - InfluxDB. By default, the username and password  is `admin`. To override the default credentials, set the following environment variables before starting the app:

* `INFLUXDB_USERNAME`
* `INFLUXDB_PASSWORD`

## Database

The app creates a default InfluxDB database called `rte-data`.



