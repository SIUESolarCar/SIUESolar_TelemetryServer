# Introduction
This repository holds the server components for the SIUE Solar Car's Telemetry System

# Server Architecture
The Server side of the SIUE Solar Racing Team's Telemetry consists of three docker containers. All three containers are to be networked together to facilitate communication between the three.

### The Interface - Grafana
This container runs our interface Grafana that is used by the team to view all of the data from the car and other sources. 

### The Database - InfluxDB
This container runs our time series database InfluxDB. This is what the car dirctly interfaces with to store data.

### The Auxiliary Data Collection - Python Script (Work in Progress)
This container running a Python script that is intended to input outside data into our database. This is often weather data.

# Setup

1.  Create and modify a file called `.env` with contents:

    ```bash
    ADMIN_USERNAME=username
    ADMIN_PASSWORD=password
    GRAFANA_PORT=3000
    INFLUXDB_PORT=8086
    ```
2. Launch the containers with the terminal.

    ```bash
    $ docker compose up

    # or when using Podman:

    $ podman compose --file compose.yaml up 
    ```