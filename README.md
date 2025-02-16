# Docker Compose Demo Project

## ⚠️ ⚠️ ⚠️
> **Note:** File .env should never be available on repository! This repository is for demo purpose only!

## Description

This project provides Docker-related files needed to build and run a demo microservices application using Docker Compose. The application includes a Spring Boot service, a Node.js service, and a PostgreSQL database.

## Getting Started

### Dependencies

* Docker  
* Docker Compose v2
* Git  
* Bash shell (for executing the health check script)  

### Installing

* Clone this repository:  
  ```bash
  git clone https://github.com/cico-12/demo-app.git
  cd demo-app/
  ```
* Ensure Docker and Docker Compose are installed and running on your system. 

### Building and pulling the Docker images
* Build and pull images using Docker Compose:
  ```bash 
  docker compose build && docker compose pull
  ```

* Verify that the images have been pulled by executing:
  ```bash
  docker images
  ```

* Expected Docker images names:
  ```bash
  demo-app_spring-boot-app:latest
  demo-app_node-app:latest
  postgres:10
  ```
### Starting the Docker containers with prebuilt images
* To start the Docker containers in foregroud with logs in terminal use:
  ```bash
  docker compose up
  ```
> **Note:** If you quit the terminal, docker containers will be exited and the services will be unavailable!

* To start the Docker containers in the background use:
  ```bash
  docker compose up -d
  ```
> **Note:** The containers will continue running even if you close the terminal!

### Verifying services
* After building and/or pulling images, verify that the Docker containers are u and running by executing: 
  ```bash
  docker ps
  ```
* Expected Docker containers names:
  ```bash
  demo-app-postgres-db
  demo-app-spring-boot-app-1
  demo-app-node-app-1
  ```
* Verify the output of the health check script:
  ```bash
  bash <(curl -s https://raw.githubusercontent.com/kkenan/basic-microservices/master/health_check.sh)
  ```
Expected output of the health script is :
  ```bash
  All checks passed. Congrats!
  ```
### Remove services and docker images
* To stop and remove containers and their volumes created use:
  ```bash
  docker compose down -v
  ```
* To remove built/pulled images use:
  ```bash
  docker rmi demo-app_spring-boot-app demo-app_node-app postgres:10
  ```
### Troubleshooting 
Check logs for troubleshooting using:
  ```bash
  docker compose logs <service-name>
  ```
Or:
  ```bash
  docker logs <container-name>
  ```
### Version History
* 1.0