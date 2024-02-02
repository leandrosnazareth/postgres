README

This repository contains a Docker Compose configuration file for setting up a local PostgreSQL database along with a PGAdmin web interface. The services are defined using version 3.8 of the Docker Compose file format.
Services
1. PostgreSQL Database (db service)

    Image: postgres
    Container Name: local_pgdb
    Restart: always
    Ports: 54320:5432
    Environment Variables:
        POSTGRES_USER: postgres
        POSTGRES_PASSWORD: admin
    Volumes:
        local_pgdata:/var/lib/postgresql/data

2. PGAdmin Web Interface (pgadmin service)

    Image: dpage/pgadmin4
    Container Name: pgadmin4_container
    Restart: always
    Ports: 5050:80
    Environment Variables:
        PGADMIN_DEFAULT_EMAIL: admin@admin.com
        PGADMIN_DEFAULT_PASSWORD: admin
    Volumes:
        pgadmin-data:/var/lib/pgadmin

Volumes

    local_pgdata: Volume for storing PostgreSQL database data.
    pgadmin-data: Volume for storing PGAdmin configuration data.

Usage

    Make sure you have Docker and Docker Compose installed.

    Clone this repository.

    Navigate to the repository directory.

    Run the following command to start the services:

    bash

    docker-compose up -d

    Access PGAdmin web interface at http://localhost:5050 using the provided credentials.

    Connect to the PostgreSQL database using the following details:
        Host: localhost
        Port: 54320
        Username: postgres
        Password: admin

Feel free to customize the configuration as needed for your development environment.
