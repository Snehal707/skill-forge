---
name: docker-container-setup
description: Set up Docker to build, run, and manage containerized applications
version: 1.0.0
metadata:
  skill_forge:
    domain: "docker"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [docker, containers, devops, virtualization]
    category: devops
---

# Docker Container Setup

## When to Use
When you need to package applications into lightweight, portable containers for consistent deployment across different environments.

## Prerequisites
- Operating system: Linux, macOS, or Windows
- Administrative privileges for installation
- Basic command line knowledge

## Procedure
1. Install Docker: `curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh`
2. Start Docker service: `sudo systemctl start docker`
3. Enable Docker to start on boot: `sudo systemctl enable docker`
4. Add user to docker group: `sudo usermod -aG docker $USER`
5. Log out and back in to refresh group membership
6. Verify installation: `docker --version`
7. Test with hello-world container: `docker run hello-world`
8. Create a simple Dockerfile for your application:
   FROM alpine:latest
   COPY . /app
   WORKDIR /app
   CMD ["your-command"]
   ```
9. Build container image: `docker build -t your-app .`
10. Run your container: `docker run -p 8080:80 your-app`

## Verification
- `docker --version` shows Docker version information
- `docker ps` lists running containers without errors
- `docker images` shows available container images

## Pitfalls
- Forgetting to add user to docker group (requires logout/login)
- Running Docker commands without sudo before group membership takes effect
- Port conflicts when mapping container ports to host ports
- Insufficient disk space for container images and volumes

## Sources
- https://www.docker.com/
- https://en.wikipedia.org/wiki/Docker_(software)
- https://www.ibm.com/think/topics/docker
- https://github.com/docker
- https://www.reddit.com/r/docker/
```