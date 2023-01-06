# Docker Course

This tutorial is designed to help beginners get started with Docker and Docker Swarm. It covers the basics of installing and using Docker, as well as more advanced topics such as container networking and deploying applications with Docker Swarm.

## Table of Contents:
1. [Introduction to Docker](#introduction-to-docker)
   - What is Docker?
   - Installing Docker
   - Basic Docker concepts
2. [Managing Docker containers](#managing-docker-containers)
   - Running a container
   - Attaching to a running container
   - Copying files from a container
   - Creating a new container
   - Viewing changes to the filesystem
   - Inspecting a container
   - Killing a container
   - Viewing logs
   - Pausing a container
   - Viewing port mappings
   - Restarting a container
   - Viewing processes in a container
3. [Managing Docker images](#managing-docker-images)
   - Listing available images
   - Removing an image
   - Viewing the history of an image
   - Removing dangling images
   - Tagging an image
4. [Executing commands in a running Docker container](#executing-commands-in-a-running-docker-container)
   - Using docker exec
5. [Container networking](#container-networking)
   - Listing networks
   - Inspecting a network
   - Creating a new network
   - Connecting a container to a network
   - Disconnecting a container from a network
   - Creating a network with a specific driver
   - Creating a network with a custom subnet
   - Creating a network with a custom IP range
   - Forcefully disconnecting a container from a network
6. [Working with Docker Compose](#working-with-docker-compose)
   - Running a command in a new container
   - Building images before starting containers
   - Recreating all containers
   - Starting containers without starting linked services
7. [Introduction to Docker Swarm](#introduction-to-docker-swarm)
   - What is Docker Swarm?
   - Initializing and managing a Swarm
8. [Working with Swarm services](#working-with-swarm-services)
   - Creating a new service
   - Inspecting a service
   - Viewing logs for a service
   - Listing all services
   - Listing tasks of a service
   - Removing a service
   - Rolling back a service
   - Scaling a service
   - Updating the configuration of a service
9. [Working with Swarm nodes](#working-with-swarm-nodes)
   - Demoting a manager node
   - Inspecting a node
   - Listing all nodes
   - Promoting a worker node
   - Updating the configuration of a node
10. [Conclusion](#conclusion)

## Introduction to Docker

### What is Docker?
Docker is a popular tool for deploying and managing applications in containers. Containers allow you to package an application and its dependencies into a single, portable unit that can be easily moved between different environments. This tutorial is designed to help beginners get started with Docker and Docker Swarm, a tool for orchestrating a cluster of Docker nodes.

### Installing Docker
Before you can use Docker, you need to install it on your system. You can find installation instructions for your specific platform in the [Docker documentation](https://docs.docker.com/get-docker/).

### Basic Docker Concepts

Docker uses images to run containers. An image is a lightweight, stand-alone, executable package that includes everything needed to run a piece of software, including the application code, libraries, dependencies, and runtime. You can think of an image as a blueprint for a container.

To run an image in a container, you can use the `docker run` command. For example:

`docker run <image_name> <command> `

This command will create a new container from the specified image, and run the specified command in the container.

## Managing Docker containers

### Running a Container

To run a container, you can use the `docker run` command. For example:

`docker run <image_name> <command> `

This command will create a new container from the specified image, and run the specified command in the container.

### Attaching to a Running Container

To attach to a running container, you can use the `docker attach` command. For example:

`docker attach <container_id> `

This command will attach your terminal to the specified container

### Copying Files from a Container

To copy files from a container, you can use the `docker cp` command. For example:

`docker cp <container_id>:<src_path> <dest_path> `

This command will copy the file at `src_path` in the container to `dest_path` on the host machine.

### Creating a New Container

To create a new container, you can use the `docker create` command. For example:

`docker create <image_name> <command> `

This command will create a new container from the specified image, but it will not start the container. To start the container, you can use the `docker start` command.

### Viewing Changes to the Filesystem

To view the changes made to the filesystem of a container, you can use the `docker diff` command. For example:

`docker diff <container_id> `

This command will show the changes made to the container's filesystem since it was created.

### Inspecting a Container

To view detailed information about a container, you can use the `docker inspect` command. For example:

`docker inspect <container_id> `

This command will display detailed information about the specified container, including its configuration, state, and resource usage.

### Killing a Container

To stop a running container, you can use the `docker kill` command. For example:

`docker kill <container_id>`

This command will send a SIGKILL signal to the container.

### Viewing Logs

To view the logs for a container, you can use the `docker logs` command. For example:

`docker logs <container_id> `

This command will display the logs for the specified container. By default, it will show the logs for the most recent run of the container. You can use the `--follow` flag to keep the logs open and display new log entries as they are written.

### Pausing a Container

To pause a running container, you can use the `docker pause` command. For example:

`docker pause <container_id>`

This command will pause the specified container, which will stop all processes within the container. You can use the `docker unpause` command to resume the container.

### Viewing Port Mappings

To view the port mappings for a container, you can use the `docker port` command. For example:

`docker port <container_id> `

This command will display the port mappings for the specified container.

### Restarting a Container

To restart a stopped container, you can use the `docker start` command. For example:

`docker start <container_id> `

This command will start the specified container.

### Viewing Processes in a Container

To view the processes running in a container, you can use the `docker top` command. For example:

`docker top <container_id>`

This command will display the processes running in the specified container.

### Stopping a Container

To stop a running container, you can use the `docker stop` command. For example:

`docker stop <container_id> `

This command will stop the specified container. Unlike `docker kill`, which sends a SIGKILL signal to the container, `docker stop` will send a SIGTERM signal to the container, which allows the processes in the container to cleanly shut down. If the processes do not respond to the SIGTERM signal after a timeout period, `docker stop` will send a SIGKILL signal to the container to force it to stop.

## Managing Docker images

### Listing Available Images

To list the available images on your system, you can use the `docker images` command. For example:

`docker images`

This command will list all the images on your system, along with their repository and tag names.

### Removing an Image

To remove an image from your system, you can use the `docker rmi` command. For example:

`docker rmi <image_name> `

This command will remove the specified image from your system.

### Viewing the History of an Image

To view the history of an image, you can use the `docker history` command. For example:

`docker history <image_name>`

This command will display the history of the specified image, showing the layers that make up the image and the commands used to create each layer.

### Removing Dangling Images

Dangling images are images that are not associated with any container. They can accumulate on your system over time and take up unnecessary disk space. To remove dangling images from your system, you can use the `docker image prune` command. For example:

`docker image prune`

This command will remove all dangling images from your system.

### Tagging an Image

To tag an image with a custom name, you can use the `docker tag` command. For example:

`docker tag <image_id> <custom_name> `

This command will tag the specified image with the custom name. This can be useful for organizing images and for publishing them to a registry.

## Executing commands in a running Docker container

To execute a command in a running Docker container, you can use the `docker exec` command. For example:

`docker exec <container_id> <command>`

This command will run the specified command in the specified container.

## Container networking

Docker provides several options for connecting containers to networks. You can use the following commands to manage container networking:

### Listing Networks

To list the networks on your system, you can use the `docker network ls` command. For example:

`docker network ls`

This command will list all the networks on your system, along with their driver and scope.

### Inspecting a Network

To view detailed information about a network, you can use the `docker network inspect` command. For example:

`docker network inspect <network_name> `

This command will display detailed information about the specified network, including its configuration, driver, and connected containers.

### Creating a New Network

To create a new network, you can use the `docker network create` command. For example:

`docker network create <network_name>`

This command will create a new network with the specified name. By default, it will use the bridge driver, which creates a separate network namespace for each container and connects them using a virtual Ethernet bridge.

### Connecting a Container to a Network

To connect a container to a network, you can use the `docker network connect` command. For example:

`docker network connect <network_name> <container_id> `

This command will connect the specified container to the specified network.

### Disconnecting a Container from a Network

To disconnect a container from a network, you can use the `docker network disconnect` command. For example:

`docker network disconnect <network_name> <container_id> `

This command will disconnect the specified container from the specified network.

### Creating a Network with a Specific Driver

To create a network with a specific driver, you can use the `--driver` flag with the `docker network create` command. For example:

`docker network create --driver <driver_name> <network_name>`

This command will create a new network with the specified driver and name. Docker supports several built-in drivers, including bridge, host, and overlay.

### Creating a Network with a Custom Subnet

To create a network with a custom subnet, you can use the `--subnet` flag with the `docker network create` command. For example:

`docker network create --subnet <subnet> <network_name>`

This command will create a new network with the specified subnet and name. The subnet should be in CIDR notation, for example `172.18.0.0/16`.

### Creating a Network with a Custom IP Range

To create a network with a custom IP range, you can use the `--ip-range` flag with the `docker network create` command. For example:

`docker network create --ip-range <range> <network_name>`

This command will create a new network with the specified IP range and name.

### Forcefully Disconnecting a Container from a Network

To forcefully disconnect a container from a network, you can use the `--force` flag with the `docker network disconnect` command. For example:

`docker network disconnect --force <network_name> <container_id> `

This command will forcibly disconnect the specified container from the specified network, even if the container is running.

## Working with Docker Compose

[Docker Compose](https://docs.docker.com/compose/) is a tool for defining and running multi-container Docker applications. You can use the following commands to work with Docker Compose:

### Running a Command in a New Container

To run a command in a new container, you can use the `docker-compose run` command. For example:

`docker-compose run <service_name> <command> `

This command will create a new container from the specified service and run the specified command in the container.

### Building Images Before Starting Containers

To build images before starting containers, you can use the `--build` flag with the `docker-compose up` command. For example:

`docker-compose up --build`

This command will build any images that have been modified since the last build, and then start the containers.

### Recreating All Containers

To recreate all the containers in a Compose application, you can use the `docker-compose up --force-recreate` command. For example:

`docker-compose up --force-recreate`

This command will stop and remove the existing containers, and then create and start new containers from the current configuration.

### Starting Containers Without Starting Linked Services

To start containers without starting linked services, you can use the `--no-deps` flag with the `docker-compose up` command. For example:

`docker-compose up --no-deps <service_name>`

This command will start the specified service, but it will not start any of the service's linked dependencies.

## Introduction to Docker Swarm

Docker Swarm is a tool for orchestrating a cluster of Docker nodes. It allows you to create and manage a group of Docker servers as a single, logical entity, making it easier to deploy and manage distributed applications.

### Initializing a Swarm

To create a new Swarm, you can use the `docker swarm init` command. For example:

`docker swarm init`

This command will initialize a new Swarm and make the current node the leader.

### Adding a Node to a Swarm

To add a new node to an existing Swarm, you can use the `docker swarm join` command. For example:

`docker swarm join --token <token> <swarm_manager_ip>:<swarm_manager_port> `

This command will add the current node to the specified Swarm as a worker.

### Removing a Node from a Swarm

To remove a node from a Swarm, you can use the `docker swarm leave` command. For example:

`docker swarm leave`

This command will remove the current node from the Swarm. If the node is a manager, it will also demote the node to a worker before removing it.

### Promoting a Worker Node to a Manager

To promote a worker node to a manager, you can use the `docker node promote` command. For example:

`docker node promote <node_id> `

This command will promote the specified worker node to a manager.

### Demoting a Manager Node to a Worker

To demote a manager node to a worker, you can use the `docker node demote` command. For example:

`docker node demote <node_id> `

This command will demote the specified manager node to a worker.

### Inspecting a Node

To view detailed information about a node, you can use the `docker node inspect` command. For example:

`docker node inspect <node_id> `

This command will display detailed information about the specified node, including its status, role, and configuration.

### Listing All Nodes

To list all the nodes in a Swarm, you can use the `docker node ls` command. For example:

`docker node ls`

This command will list all the nodes in the Swarm, along with their ID, status, and role.

### Updating the Configuration of a Node

To update the configuration of a node, you can use the `docker node update` command. For example:

`docker node update <node_id> <options> `

This command will update the specified node with the specified options. The options can include changes to the node's availability, labels, and other settings.

## Working with Swarm services

To create and manage Swarm services, you can use the following commands:

### Creating a New Service

To create a new service in a Swarm, you can use the `docker service create` command. For example:

`docker service create <image_name>`

This command will create a new service in the Swarm, using the specified image.

### Inspecting a Service

To view detailed information about a service, you can use the `docker service inspect` command. For example:

`docker service inspect <service_name> `

This command will display detailed information about the specified service, including its configuration, task state, and network settings.

### Viewing Logs for a Service

To view the logs for a service, you can use the `docker service logs` command. For example:

`docker service logs <service_name> `

This command will display the logs for the specified service. By default, it will show the logs for the most recent run of the service. You can use the `--follow` flag to keep the logs open and display new log entries as they are written.

### Listing All Services

To list all the services in a Swarm, you can use the `docker service ls` command. For example:

`docker service ls`

This command will list all the services in the Swarm, along with their ID, name, and mode.

### Listing Tasks of a Service

To list the tasks of a service, you can use the `docker service ps` command. For example:

`docker service ps <service_name> `

This command will list the tasks of the specified service, along with their ID, node, and current state.

### Removing a Service

To remove a service from the Swarm, you can use the `docker service rm` command. For example:

`docker service rm <service_name>`

This command will remove the specified service from the Swarm.

### Rolling Back a Service

To roll back a service to a previous configuration, you can use the `docker service rollback` command. For example:

`docker service rollback <service_name> `

This command will roll back the specified service to the previous configuration.

### Scaling a Service

To scale a service up or down, you can use the `docker service scale` command. For example:

`docker service scale <service_name>=<number_of_replicas> `

This command will scale the specified service to the specified number of replicas.

### Updating the Configuration of a Service

To update the configuration of a service, you can use the `docker service update` command. For example:

`docker service update <service_name> <options> `

This command will update the specified service with the specified options. The options can include changes to the service's image, networks, environment variables, and other settings.

## Working with Swarm nodes

### Removing a Node from a Swarm

To remove a node from a Swarm, you can use the `docker node rm` command. For example:

`docker node rm <node_id>`

This command will remove the specified node from the Swarm. If the node is a manager, it will be demoted to a worker before being removed. If the node is running tasks, those tasks will be rescheduled on other nodes before the node is removed.

### Changing the Availability of a Node

To change the availability of a node, you can use the `docker node update` command with the `--availability` flag. For example:

`docker node update --availability <availability> <node_id> `

This command will set the availability of the specified node to the specified value. The possible values for `availability` are `active`, `pause`, and `drain`. An `active` node is a normal node that can run tasks. A `pause` node is a node that can't run new tasks, but existing tasks will continue to run. A `drain` node is a node that will stop running new tasks, and existing tasks will be rescheduled on other nodes.

### Adding Labels to a Node

To add labels to a node, you can use the `docker node update` command with the `--label-add` flag. For example:

`docker node update --label-add <label_name>=<label_value> <node_id> `

This command will add the specified label to the specified node. Labels are key-value pairs that can be used to organize and filter nodes.

### Removing Labels from a Node

To remove labels from a node, you can use the `docker node update` command with the `--label-rm` flag. For example:

`docker node update --label-rm <label_name> <node_id> `

This command will remove the specified label from the specified node.

## Conclusion
In this tutorial, you learned the basics of Docker and Docker Swarm, and how to use them to create and manage a cluster of Docker nodes. You learned how to run and manage Docker containers, how to work with Docker images, how to use container networking, and how to deploy and manage applications with Docker Swarm.

I hope this tutorial has been helpful in getting you started with Docker and Docker Swarm, and that you feel confident using these tools to build and deploy your own applications. Let me know if you have any questions or if there is anything else I can help with.

## References
- Docker documentation
- Personal experience
