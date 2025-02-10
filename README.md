# Docker Overview

## What is Docker?

Docker is an open-source containerization platfrom that is used for running, developing and shipping the applications.

## What is a Container?

Containers are the lightweight machines which contains packages of software and its dependencies that are required to run an software application across different environments.

## Why are Containers lightweight when compared to VMs?

- Shared Host OS: Containers share the host os kernel system allows for faster startup and reduced overhead compared to VMs.
- Isolation: Contaners remain isolated from each other while sharing the host os, which makes them efficient. 
- Virtual Machines: VMs emulate entire physical computer including its own operating system and require more resources to run.

## Key Components of Docker

Let us understand the Key Components of Docker.

- Docker Daemon: Docker Daemon is the important component of the Docker. It is responsible for creating Docker Images and running the containers.
- Docker CLI: Docker CLI allows users to communicate with the Docker Daemon.
- Docker Registry: Docker Registry is a central hub that is used to store and share the images around the world.

## Life Cycle of Docker

- Docker build --> This command is used to build the Docker Images from the Dockerfile.
- Docker run --> This command is used to run the image as a container
- Docker push --> This command is used to push the image to the Docker registry.

## What is Docker Image?

Docker Image is a read only template which is built from the Dockerfile. It contains all the packages and dependencies that are required to run the container.

## Common Docker Commands

### Image Commands

- docker pull --> is used to pull the images from Docker registry
- docker images --> is used to list all the images
- docker rmi --> is used to delete the images.

### Container Commands

- docker run -d --> is used to run the image as a container in the detach mode.
- docker run -it --> is used to run the image as a container in the interactive mode.
- docker exec -it --> is used to login to the container.
- docker ps -a --> is used to list all the containers.
- docker ps --> is used to list all the running containers.
- docker start --> is used to start the container.
- docker stop --> is used to stop the container.
- docker rm --> is used to delete the containers.

### Utility Commands

- docker system prune --> is used to remove all the docker dangling(unused) resources.
- docker logs --> is used to check the logs of the container.
- docker stats --> is used to check the resource utilization of the container.
- docker inspect --> is used to inspect the container.

