# Docker Commands from Beginner to Advanced

## Beginner Commands

### `docker --version`

- Displays the installed Docker version.

### `docker info`

- Provides detailed information about the Docker installation, including the number of containers, images, and the Docker daemon configuration.

### `docker help`

- Lists all available Docker commands and options.

### `docker pull <image_name>`

- Downloads a Docker image from Docker Hub (or other configured Docker registry) to your local machine.
- Example: `docker pull nginx`

### `docker images`

- Lists all Docker images stored on the local machine.

### `docker run <image_name>`

- Creates and starts a new container from the specified image.
- Example: `docker run nginx`

### `docker ps`

- Lists all currently running containers.

### `docker ps -a`

- Lists all containers, including those that are stopped.

### `docker stop <container_id>`

- Stops a running container using its container ID or name.

### `docker rm <container_id>`

- Removes a stopped container using its container ID or name.

### `docker rmi <image_name>`

- Removes a Docker image from the local machine.
- Example: `docker rmi nginx`

### `docker tag <source_image> <target_image>`

- Tags an image with a new name.
- Example: `docker tag myapp:latest myapp:v1.0`

### `docker login`

- Logs in to a Docker registry.

### `docker logout`

- Logs out from a Docker registry.

## Intermediate Commands

### `docker build -t <image_name> .`

- Builds a Docker image from a Dockerfile in the current directory and tags it with a name.
- Example: `docker build -t myapp .`

### `docker run [OPTIONS] <image_name>`

- Creates and starts a new container with specified options.
- Example: `docker run --name my_nginx -d -p 8080:80 nginx`

### `docker exec -it <container_id> /bin/bash`

- Starts a bash shell inside a running container, allowing you to interact with the container's filesystem and processes.

### `docker logs <container_id>`

- Displays the logs of a specific container.

### `docker inspect <container_id>`

- Provides detailed information about a container, including its configuration and state.

### `docker-compose up`

- Starts all the services defined in a `docker-compose.yml` file.
- Use `-d` to run in detached mode.
- Example: `docker-compose up -d`

### `docker-compose down`

- Stops and removes all containers, networks, and volumes defined in a `docker-compose.yml` file.

### `docker network ls`

- Lists all Docker networks on the local machine.

### `docker network create <network_name>`

- Creates a new Docker network.
- Example: `docker network create mynetwork`

### `docker network connect <network_name> <container_id>`

- Connects a container to a specific Docker network.

### `docker volume ls`

- Lists all Docker volumes on the local machine.

### `docker volume create <volume_name>`

- Creates a new Docker volume.
- Example: `docker volume create myvolume`

### `docker stats [OPTIONS]`

- Displays real-time resource usage statistics for containers.
- Example: `docker stats --all`

### `docker cp <container_id>:<container_path> <host_path>`

- Copies files or directories between a container and the host.

### `docker stop <container_id>`

- Stops a running container using its container ID or name.

### `docker rm <container_id>`

- Removes a stopped container using its container ID or name.

## Advanced Commands

### `docker service create --name <service_name> <image_name>`

- Creates a new service in a Docker swarm.
- Example: `docker service create --name myservice nginx`

### `docker swarm init`

- Initializes a new Docker swarm on the current machine.

### `docker swarm join --token <token> <manager_ip>:<port>`

- Joins a worker node to an existing Docker swarm using a token provided by the swarm manager.

### `docker stack deploy -c <compose_file> <stack_name>`

- Deploys a stack (a group of services) to a Docker swarm using a Docker Compose file.
- Example: `docker stack deploy -c docker-compose.yml mystack`

### `docker stack rm <stack_name>`

- Removes a stack from a Docker swarm.

### `docker secret create <secret_name> <secret_file>`

- Creates a new secret in a Docker swarm.
- Example: `docker secret create mysecret /path/to/secret.txt`

### `docker secret ls`

- Lists all secrets in a Docker swarm.

### `docker config create <config_name> <config_file>`

- Creates a new config in a Docker swarm.
- Example: `docker config create myconfig /path/to/config.txt`

### `docker config ls`

- Lists all configs in a Docker swarm.

### `docker prune`

- Removes unused Docker objects (containers, networks, images, and volumes) to free up space.

### `docker system df`

- Displays the amount of disk space used by Docker objects.

### `docker system prune`

- Cleans up all unused Docker objects, including dangling images and stopped containers.

### `docker save -o <file> <image_name>`

- Exports an image to a tar archive.
- Example: `docker save -o myapp.tar myapp:latest`

### `docker load -i <file>`

- Imports an image from a tar archive.
- Example: `docker load -i myapp.tar`

### `docker export -o <file> <container_id>`

- Exports a container’s filesystem as a tar archive.
- Example: `docker export -o mycontainer.tar mycontainer`

### `docker import <file>`

- Imports a tarball to create a filesystem image.

### `docker checkpoint create <container_name> <checkpoint_name>`

- Creates a checkpoint from a running container.

### `docker checkpoint ls <container_name>`

- Lists checkpoints for a container.

### `docker checkpoint rm <container_name> <checkpoint_name>`

- Deletes a specific checkpoint from a container.

### `docker container update [OPTIONS] <container_id>`

- Updates resource limits for a container.
- Example: `docker container update --memory 512m mycontainer`

### `docker diff <container_id>`

- Shows changes made to a container’s filesystem.
