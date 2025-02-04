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

## Practical Implementation of Docker Volumes

## Example: Running an NGINX Container without a Volume

- Lets run a contianer without a volume

```bash
   docker run -d -p 80:80 --name nginx_noVolume nginx:latest
  ```

- Enter the container and modify the index.html file of the nginx

```bash
   docker exec -it nginx_noVolume /bin/bash
   cd /usr/share/nginx/html
   echo "Hey, this is the app with no Docker volume" > index.html
  ```

- Now Access the application at http://localhost:80.

- Stop and Start the container.

```bash
   docker stop nginx_noVolume
   docker start nginx_noVolume
  ```

- Access the application again using http://localhost:80/

- We can see the application is still accessible. Which means the data is not lost when you stop and start the container

- Now lets try to remove the container and recreate it.

```bash
   docker stop nginx_noVolume
   docker rm nginx_noVolume
   docker run -d -p 80:80 --name nginx_noVolume nginx:latest
  ```

- Now accessing http://localhost:80 will show the default NGINX page, proving that data was lost.

## Example: Running an NGINX Container with a Volume

- Create a volume:

```bash
   docker volume create demo_volume
  ```

- Attach the volume and run the container:

```bash
   docker run -d -v demo_volume:/usr/share/nginx/html --name nginx_withVolume nginx:latest
  ```

- Modify the content inside the container:

```bash
   docker exec -it nginx_withVolume /bin/bash
   cd /usr/share/nginx/html
   echo "Hey,This is the app with docker volume" > index.html
  ```
- Access the app using http://locahost:80/

- Remove and recreate the container:

```bash
   docker stop nginx_withVolume
   docker rm nginx_withVolume
   docker run -d -v demo_volume:/usr/share/nginx/html --name nginx_withVolume nginx:latest
  ```

- Now access the application using http://localhost:80/

- Data persists, and the modified application content is still accessible.

## 2. Example: Bind Mount Usage

- Create a directory on the host and run the container by mounting the host directory.

```bash
   mkdir /path/hostdirectory
   docker run -d -v /path/hostdirectory:/usr/share/nginx/html -p 80:80 --name nginx_withBind nginx:latest
  ```
- Add a file to the host directory:

```bash
   echo "Hello from Bind Mount!" > /path/hostdirectory/index.html
  ```

- Access the container and verify the changes:

```bash
   docker exec -it nginx_withBind /bin/bash
   ls /usr/share/nginx/html
  ```
- The file added on the host will be visible inside the container.

