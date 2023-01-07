# Docker Cheatsheet for Beginners

This cheatsheet is a beginner-friendly guide to Docker commands, covering the most commonly used commands for running and managing containers, working with images, and networking. It also includes a section on Docker Compose, which is a tool for defining and running multi-container applications. This cheatsheet is designed to help new users get started with Docker and become familiar with the most essential commands in a concise and easy-to-follow format.

## Running and managing containers

- `docker run <image>`: Run a container from an image
- `docker start <container_id>`: Start a stopped container
- `docker stop <container_id>`: Stop a running container
- `docker kill <container_id>`: Forcefully stop a running container
- `docker attach <container_id>`: Attach to a running container
- `docker exec -it <container_id> <command>`: Run a command in an interactive shell in a running container
- `docker rm <container_id>`: Remove a stopped container
- `docker inspect <container_id>`: Inspect a container
- `docker logs <container_id>`: View logs for a container
- `docker top <container_id>`: View processes in a container

## Managing images

- `docker images`: List available images
- `docker rmi <image_id>`: Remove an image
- `docker history <image_id>`: View the history of an image
- `docker pull <image>`: Download an image from a registry (e.g., Docker Hub)
- `docker build -t <name> .`: Build an image from a `Dockerfile` in the current directory and give it the specified name
- `docker push <image>`: Push an image to a registry
- `docker tag <image_id> <tag>`: Tag an image

## Managing container resources

- `docker run --cpus=<num> <image>`: Limit the number of CPU cores available to a container
- `docker run --memory=<size> <image>`: Limit the amount of memory available to a container

## Managing container metadata

- `docker run --name=<name> <image>`: Assign a name to a container
- `docker run -e <key>=<value> <image>`: Set an environment variable in a container

## Managing container users

- `docker run --user=<user> <image>`: Run a container as a specific user
- `docker run --user=<uid>:<gid> <image>`: Run a container as a specific user and group

## Managing container volumes

- `docker run -v <host_path>:<container_path> <image>`: Bind mount a host path to a container path
- `docker run -v <host_path>:<container_path>:ro <image>`: Bind mount a host path to a container path in read-only mode
- `docker run -v <container_path> <image>`: Create a data volume in a container
- `docker run --mount type=volume,src=<volume_name>,dst=<container_path> <image>`: Use a named volume in a container

## Managing container networks

- `docker run --network <network> <image>`: Connect a container to a network
- `docker run --network <network> --ip <ip_address> <image>`: Connect a container to a network and specify its IP address
- `docker network create <network>`: Create a new network
- `docker network rm <network>`: Remove a network

## Managing container ports

- `docker run -p <host_port>:<container_port> <image>`: Publish a container port to the host
- `docker port <container_id>`: View the port mappings for a container

## Managing container security

- `docker run --security-opt=<option> <image>`: Set a security option for a container

## Managing container health

- `docker run --health-cmd=<command> <image>`: Set a command to be used to check the health of a container

## Managing container capabilities

- `docker run --cap-add=<capability> <image>`: Add a capability to a container
- `docker run --cap-drop=<capability> <image>`: Drop a capability from a container

## Managing container isolation

- `docker run --isolation=<isolation> <image>`: Set the isolation level for a container

## Managing container storage

- `docker run --storage-opt=<option> <image>`: Set a storage option for a container

## Managing container labels

- `docker run --label <key>=<value> <image>`: Add a label to a container

## Managing container UTS namespace

- `docker run --uts=<uts> <image>`: Set the UTS namespace mode for a container

## Managing a Swarm

- `docker swarm init`: Initialize a Swarm
- `docker swarm join`: Join a Swarm as a worker
- `docker swarm join-token worker`: View the command to join a Swarm as a worker
- `docker swarm leave`: Leave a Swarm

## Managing Swarm services

- `docker service create <image>`: Create a new service
- `docker service inspect <service_id>`: Inspect a service
- `docker service logs <service_id>`: View logs for a service
- `docker service ls`: List all services
- `docker service tasks <service_id>`: List tasks of a service
- `docker service rm <service_id>`: Remove a service
- `docker service rollback <service_id>`: Roll back a service
- `docker service scale <service_id>=<replicas>`: Scale a service
- `docker service update <service_id> <options>`: Update the configuration of a service

## Managing Swarm nodes

- `docker node demote <node_id>`: Demote a manager node
- `docker node inspect <node_id>`: Inspect a node
- `docker node ls`: List all nodes
- `docker node promote <node_id>`: Promote a worker node
- `docker node update <node_id> <options>`: Update the configuration of a node

## Managing Compose projects

- `docker-compose up`: Start and recreate containers
- `docker-compose up -d`: Start containers in detached mode
- `docker-compose up --no-recreate`: Start containers without recreating them
- `docker-compose up --force-recreate`: Recreate containers before starting them
- `docker-compose down`: Stop and remove containers
- `docker-compose stop`: Stop containers
- `docker-compose start`: Start stopped containers
- `docker-compose restart`: Restart running containers
- `docker-compose build`: Build images before starting containers
- `docker-compose pull`: Pull images before starting containers

## Managing Compose services

- `docker-compose run <service> <command>`: Run a command in a new container
- `docker-compose exec <service> <command>`: Run a command in an existing container
- `docker-compose up --no-deps <service>`: Start a service without starting linked services

## Managing Compose configuration

- `docker-compose config`: Validate and view the Compose file
- `docker-compose config > <file>`: Generate a Compose file in the specified format

## Managing Compose environments

- `docker-compose -f <file> <command>`: Use the specified Compose file for the command
- `docker-compose --env-file <file> <command>`: Load environment variables from the specified file for the command
- `docker-compose --project-name <name> <command>`: Set the project name for the command
