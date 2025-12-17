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

