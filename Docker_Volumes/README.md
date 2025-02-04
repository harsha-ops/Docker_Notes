# Docker Volumes and Bind Mounts

## What is a Docker Volume?

Docker Volumes are used to persistent the data generated or used in the containers. Since containers are ephemeral by nature which means any data stored inside a container is lost when the container goes down or removed. To overcome this challenge, we can make use of Docker volume.

## Key Benefits of Docker Volumes:

- Data Persistence: Ensure Data remains persistent even after container removal.

- Container Portability: Volumes can be shared between containers.

## What is Bind Mount?

Bind mount is a concept where we can mount our host direcrtory to a directory inside the container. This approach enables real-time synchronization between the host and container, simplifying development tasks.

## Advantages of Bind Mounts:

- Direct Editing: Modify files on the host without needing to enter the container.
- Real-Time Changes: Changes in the host directory are immediately reflected in the mounted container directory.
