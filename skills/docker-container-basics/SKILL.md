---
name: docker-container-basics
description: Build and run containerized applications using Docker for consistent deployment environments
version: 1.0.0
metadata:
  skill_forge:
    domain: "docker"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [docker, containers, devops, deployment]
    category: devops
---

# Docker Container Basics

## When to Use
- You need to package an application with its dependencies for consistent deployment
- You want to isolate applications from the host system
- You're setting up development environments that match production
- You need to deploy applications across different operating systems

## Prerequisites
- Docker Desktop installed on your system
- Basic command line familiarity
- Application code ready to containerize

## Procedure
1. Create a Dockerfile in your project root: `touch Dockerfile`
2. Define the base image and dependencies:
   FROM node:16-alpine
   WORKDIR /app
   COPY package*.json ./
   RUN npm install
   COPY . .
   EXPOSE 3000
   CMD ["npm", "start"]
   ```
3. Build the Docker image: `docker build -t my-app:latest .`
4. Run the container: `docker run -d -p 3000:3000 --name my-app-container my-app:latest`
5. Verify container is running: `docker ps`
6. View application logs: `docker logs my-app-container`

## Verification
- Container appears in `docker ps` output with "Up" status
- Application responds at `localhost:3000` (or configured port)
- `docker logs container-name` shows expected startup messages

## Pitfalls
- Forgetting to expose ports in Dockerfile and map them when running
- Not using .dockerignore leading to large image sizes
- Running containers as root user (security risk)
- Not cleaning up stopped containers and unused images

## Sources
- https://www.docker.com/
- https://en.wikipedia.org/wiki/Docker_(software)
- https://www.ibm.com/think/topics/docker
- https://github.com/docker
```