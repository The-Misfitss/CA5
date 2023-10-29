# CA5

# PostgreSQL Database Service with Docker

This repository contains the Docker configuration and scripts to set up a PostgreSQL database service using Docker. It includes a Dockerfile, an initialization SQL script, and a Jenkinsfile for building, tagging and pushing the PostgreSQL Docker image to a container registry (Docker Hub).

## Dockerfile

The `Dockerfile` is used to build a Docker image for the PostgreSQL database service. It uses the official PostgreSQL image as the base image and sets environment variables for database configuration. Additionally, it copies an initialization SQL script to set up the database schema and populate initial data.

## Initialization SQL Script

The `init.sql` script is used to create a table called `students` in the database, insert data into the table, and perform a select query. This script is copied into the Docker container and executed during initialization.

## Jenkins

Created a Jenkins Pipeline to automate the process of building, tagging and pushing the PostgreSQL Docker image to a container registry (Docker Hub). The pipeline is triggered on a specified branch and includes the following steps:

1. Checkout code from the repository.
2. Login to Docker Hub using your credentials.
3. Build the Docker image from the Dockerfile.
4. Tag the Docker image.
5. Push the Docker image to the container registry.

Use these guidelines to set up and run your PostgreSQL database service using Docker with ease.
