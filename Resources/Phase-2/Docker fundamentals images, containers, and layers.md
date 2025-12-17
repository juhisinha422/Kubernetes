# Docker Fundamentals: Images, Containers, and Layers

## Overview

Docker is a platform for developing, shipping, and running applications inside containers. Understanding Docker fundamentals such as images, containers, and layers is essential for working with Docker. This guide will help you understand these core concepts.

## Table of Contents

1. [Docker Images](#docker-images)
2. [Docker Containers](#docker-containers)
3. [Docker Layers](#docker-layers)

---

## 1. Docker Images

### What is a Docker Image?

- **Docker Image**: A Docker image is a lightweight, standalone, executable package that includes everything needed to run a piece of software (code, runtime, libraries, and dependencies).
- Docker images are the blueprint or template used to create containers.

### How Docker Images Work

- Images are read-only and can be used to create multiple containers.
- Images are typically built from a **Dockerfile**, which is a text file that contains the instructions for building the image.

### Image Creation Process

1. **Base Image**: Choose a base image, such as `ubuntu`, `node`, or `python`, that provides the environment you need.
2. **Add Files**: Copy your application files and dependencies into the image.
3. **Define the Command**: Specify the command or process to run when the container starts.

#### Example Dockerfile:

```Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14

# Set the working directory inside the container
WORKDIR /usr/src/app

# Copy the package.json file to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the port that the app will run on
EXPOSE 8080

# Define the command to run the app
CMD ["node", "app.js"]
```

### Pulling Images

To use a pre-built image from a registry like Docker Hub, you can pull the image using the docker pull command:

docker pull node:14

## 2. Docker Containers
**What is a Docker Container?**

**Docker Container:** A container is a running instance of a Docker image. Containers provide a lightweight, isolated environment for running applications.

Unlike virtual machines, containers share the host system’s OS kernel, making them more efficient.

## Container Lifecycle

**Create:** A container is created from a Docker image using the docker create or docker run command.

**Run:** A container starts running once created, executing the command defined in the image.

**Stop:** You can stop a running container with docker stop <container_id>.

**Remove:** To remove a container, use docker rm <container_id>.

**Example:**

Running a container:

docker run -d --name my-container -p 8080:8080 node:14

This runs the node:14 image, names the container my-container, and binds port 8080 on the container to port 8080 on the host.

## Container vs Image

**Image:** A static file that contains everything needed to run a program (code, libraries, etc.).

**Container:** A running instance of an image with its own file system and processes.

## 3. Docker Layers
**What are Docker Layers?**

**Docker Layers:** Each step in a Dockerfile corresponds to a layer in the image. Layers are used to build up the image incrementally.

Layers are cached to speed up the build process. If a layer hasn’t changed, Docker uses the cached version, which makes builds faster.

**How Docker Layers Work**

Each command in a Dockerfile (e.g., RUN, COPY, ADD) creates a new layer.

**Layer Caching:** Docker caches layers to avoid re-running unchanged instructions. This helps speed up subsequent builds.

**Image Layering:** When an image is built, each layer is stacked on top of the previous one.

**Example:**

If a Dockerfile has these three commands:

```
FROM ubuntu:20.04
RUN apt-get update && apt-get install -y curl
COPY . /app
```

The first layer is the ubuntu:20.04 base image.

The second layer contains the changes made by the RUN command (installing curl).

The third layer contains the copied application files (COPY).
