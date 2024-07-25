# Introduction
This repository holds the server components for the SIUE Solar Car's Telemetry System

# Server Architecture
The Server side of the SIUE Solar Racing Team's Telemetry consists of three docker containers. All three containers are to be networked together to facilitate communication between the three.

### The Database - InfluxDB
This container runs our time series database InfluxDB. This is what the car dirctly interfaces with to store data.

### The Interface - Grafana
This container runs our interface Grafana that is used by the team to view all of the data from the car and other sources. 

### The Auxiliary Data Collection - Python Script
This container running a Python script that is intended to input outside data into our database. This is often weather data.

# Setup Process

1.  Create a file called `.evn` in your project directory and paste the following code in:

    ``` 
    GRAFANA_USERNAME=username
    GRAFANA_PASSWORD=password
    INFLUXDB_USERNAME=username
    INFLUXDB_PASSWORD=password
    ```

2. Modify the `.evn` file's usernames and passwords. 

> [!CAUTION]
> Use secure passwords this can be access on the world wide web. Be Smart

3. Run the Docker Compose in the terminal.

    ```
    $ docker compose up
    ```