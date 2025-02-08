# Docker Multi-Arch Build

Docker Multi-Arch builds allows users to create Docker images that support multiple architectures, such as amd64, arm64 and more. This ensures that your application can run on various devices and platforms without needing seperate builds.

## Advantages of Multi-Arch Builds

- Cross-Platfrom Compatibilty: Support different platforms with a single image
- Developer Covenience: Simplify build and deployment pipelines

## Practical Steps for Multi-Arch Builds

Install Docker Buildx:

```bash
sudo apt install docker-buildx
docker builder ls
  ```

Create a Multi-Arch platform using the below command:

```bash
docker buildx create --name multiarch --platform linux/amd64,linux/arm64 --driver docker-containerc --bootstrap --use
docker builder ls
  ```

Create a Multi-Arch Image and push to the Docker hub.

```bash
docker buildx build --platform linux/amd64,linux/arm64 --push -t harsha6798/docker_multiarch .
  ```
