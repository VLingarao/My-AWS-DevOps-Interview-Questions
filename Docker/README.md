---

# Docker on EC2 – 2 Years DevOps Engineer Knowledge & Practice Guide

## Docker Overview

Docker is an **open-source containerization platform** used to package applications with their dependencies into lightweight containers. It enables **consistent deployment**, **faster CI/CD**, and **environment parity** across development, testing, and production.

---

## 1. Docker Commands (2 Years Experience Level)

### Image & Container Basics

1. `docker --version` – Check installed Docker version
2. `docker version` – Display Docker client and server details
3. `docker info` – Show Docker system-wide information
4. `docker pull <image>` – Download image from Docker registry
5. `docker images` – List all Docker images
6. `docker rmi <image>` – Remove Docker image

---

### Container Lifecycle

7. `docker run <image>` – Create and start a container
8. `docker run -dt <image>` – Run container in detached mode
9. `docker ps` – List running containers
10. `docker ps -a` – List all containers
11. `docker start <container>` – Start stopped container
12. `docker stop <container>` – Stop running container
13. `docker restart <container>` – Restart container
14. `docker rm <container>` – Remove container
15. `docker rm -f <container>` – Force remove container

---

### Port & Network

16. `docker run -p 8080:80 <image>` – Port mapping (host → container)
17. `docker inspect <container>` – View container network & metadata
18. `docker network ls` – List Docker networks
19. `docker network inspect <network>` – Inspect network details

---

### Debugging & Monitoring

20. `docker logs <container>` – View container logs
21. `docker logs -f <container>` – Follow logs live
22. `docker exec -it <container> /bin/bash` – Access running container
23. `docker stats` – View container CPU & memory usage

---

### Cleanup & Maintenance

24. `docker container prune` – Remove stopped containers
25. `docker image prune` – Remove unused images
26. `docker system prune` – Clean unused Docker resources

---

### Dockerfile & Build

27. `docker build -t <image_name> .` – Build image from Dockerfile
28. `docker build -f Dockerfile.dev -t app-dev .` – Custom Dockerfile
29. `docker tag <image> <repo>:<tag>` – Tag Docker image

---

### Registry (Docker Hub / ECR)

30. `docker login` – Authenticate to Docker registry
31. `docker push <image>` – Push image to registry
32. `docker pull <image>` – Pull image from registry

---

## 2. Docker Important Topics Covered (2 Years DevOps Engineer Level)

A **2-year DevOps engineer is expected to KNOW and EXPLAIN**:

1. Docker architecture (Client, Daemon, Registry)
2. Difference between **VMs vs Containers**
3. Image vs Container
4. Dockerfile instructions

   * `FROM`, `RUN`, `COPY`, `ADD`, `CMD`, `ENTRYPOINT`, `EXPOSE`, `ENV`
5. CMD vs ENTRYPOINT (very common interview question)
6. Docker networking

   * Bridge
   * Host
7. Port mapping and port conflicts
8. Docker volumes vs bind mounts
9. Container logs & troubleshooting
10. Resource limits (CPU, Memory)
11. Multi-stage Docker builds
12. Docker Compose (basic understanding)
13. Docker security basics

* Non-root containers
* Minimal base images

14. Docker in CI/CD pipelines

* Jenkins + Docker

15. Docker registry

* Docker Hub
* AWS ECR

16. Difference between `docker run` and `docker start`
17. Docker container lifecycle
18. Container persistence & stateless nature
19. Real-world Docker issues & fixes
20. Docker → Kubernetes readiness concepts

---

## 3. Docker Task List (Must Practice – 2 Years DevOps Engineer)

These are **mandatory hands-on tasks** a 2-year DevOps engineer **must have practiced**.

---

### Foundation Tasks

1. Create an EC2 instance and install Docker
2. Enable Docker service and verify installation
3. Run nginx container and access via browser
4. Understand port conflicts on EC2

---

### Container Management

5. Start, stop, restart, and remove containers
6. Inspect container metadata and networking
7. View and analyze container logs
8. Access running container using `docker exec`

---

### Image & Dockerfile Tasks

9. Create a Dockerfile for Python Flask application
10. Build and run Flask app container
11. Modify code and rebuild image
12. Use `.dockerignore` file

---

### Java & Maven Docker Tasks

13. Dockerize a Java Maven application
14. Build JAR using Maven inside Docker
15. Use multi-stage Dockerfile for Java app

---

### Volumes & Networking

16. Use Docker volumes for data persistence
17. Test container-to-container communication
18. Create custom bridge network

---

### Registry & CI/CD

19. Push Docker image to Docker Hub
20. Create AWS ECR repository and push image
21. Jenkins pipeline to build Docker image
22. Jenkins pipeline to push image to registry

---

### Advanced & Production Tasks

23. Limit container CPU and memory
24. Run Jenkins inside Docker
25. Scan Docker images (basic security)
26. Docker Compose for multi-container app
27. Migrate Docker app toward Kubernetes

---

## 2-Year DevOps Engineer Readiness Check

You are **2-year Docker-ready** if you can:

* Write Dockerfile without Google
* Debug container failures
* Explain CMD vs ENTRYPOINT
* Integrate Docker with Jenkins
* Push images to ECR
* Run production-style containers on EC2

---

### What I Recommend Next

1. **Java + Maven Multi-stage Dockerfile**
2. **Docker Compose real project**
3. **Jenkins → Docker → ECR pipeline**
4. **Docker interview Q&A (2 years)**
5. **Docker to Kubernetes transition**
