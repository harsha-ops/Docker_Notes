# DOCKER COMPOSE

Docker Compose is a tool used to define and manage multi-container applications. It allows users to run multiple containers simultaneously by describing the resources, networks and volumes required in a simple YAML file.

## Benefits of Docker Compose

- Simplified Workflow: Easily run and manage multiple services.
- Environment Configuration: Define complex service relationships and configurations.
- Consistency: Ensure consistent application setup across environments.

## Use Case Example

Imagine deploying both front-end and back-end simultaneously.

- Front-end application running on one-container.
- Back-end API running on another container.

Refer the compose.yml file where we defined nginx,python and redis containers.

## Running Docker Compose

Start the services:

```bash
docker-compose up
  ```

Stop the services:

```bash
docker-compose down
  ```