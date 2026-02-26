```markdown
---
name: docker-container-setup
description: Set up and run a basic Docker container application for development and deployment.
metadata:
  skill_forge:
    domain: "docker"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
    version: "1.0.0"
  hermes:
    tags:
      - docker
      - containers
      - devops
      - virtualization
    category: devops
---

# Docker Container Setup

## When to Use
When you need to package an application with its dependencies into a lightweight, portable container for consistent deployment across different environments.

## Prerequisites
- Docker Desktop installed (download from docker.com for Windows/Mac/Linux)
- Basic command line knowledge
- Administrative/sudo privileges for installation

## Procedure
1. Verify Docker installation: `docker --version`
2. Pull a base image: `docker pull ubuntu:latest`
3. Create a Dockerfile in your project directory:
   ```
   FROM ubuntu:latest
   RUN apt-get update && apt-get install -y curl
   WORKDIR /app
   COPY . /app
   CMD ["echo", "Hello from Docker"]
   ```
4. Build the container: `docker build -t my-app .`
5. Run the container: `docker run my-app`
6. List running containers: `docker ps`
7. Stop container: `docker stop <container-id>`

## Verification
- `docker images` shows your built image
- `docker ps -a` shows container execution history
- Container outputs expected message when run

## Pitfalls
- Missing Dockerfile in build directory
- Port conflicts when exposing services
- Permission issues with file copying
- Large image sizes from unnecessary packages
- Not cleaning up stopped containers and unused images

## Sources
- https://www.docker.com/
- https://en.wikipedia.org/wiki/Docker_(software)
- https://www.ibm.com/think/topics/docker
- https://github.com/docker
```