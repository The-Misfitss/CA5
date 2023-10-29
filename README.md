# Title: Jenkins Pipeline for Running Docker Containers

# Overview
This GitHub README provides a concise explanation of a Jenkins pipeline for running Docker containers. The pipeline checks for the existence of specified Docker images, pulls them if they don't exist, and runs containers with proper configurations.

# Jenkins Pipeline
The Jenkins pipeline consists of the following key stages:

## Stage 1: Check and Pull Docker Images
In this stage, the pipeline checks for the existence of Docker images and pulls them if they are not found on the local system. Two images are checked: jawwadhabib/ca4-app:latest and jawwadhabib/ca4-postgres:latest.

## Stage 2: Run Docker Containers
This stage runs two Docker containers:

ca4-postgres: A PostgreSQL container is started with port mapping to host port 5432.
ca4-app: An application container is launched with port mapping from 3000 to 5000 and an environment variable DATABASE_URL is set based on the provided configuration.
# Post-Execution Cleanup
After the execution of the pipeline, the containers are stopped and removed to ensure a clean environment.

# Usage
To use this Jenkins pipeline, you need to set up a Jenkins job with a Jenkinsfile containing the provided pipeline script. Ensure that Docker is properly configured on the Jenkins server and the required Docker images are available on Docker Hub.
