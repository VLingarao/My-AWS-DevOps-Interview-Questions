# Project 1: Simple Web Server using Docker & Nginx

## Project Name

**docker-nginx-simple-webserver**

---

## Project Objective

The goal of this project is to understand Docker basics by creating and running a simple **Nginx web server** inside a Docker container and accessing it from the local browser.

This project helps beginners learn:

* What Docker images and containers are
* How to write a Dockerfile
* How to expose ports
* How to run and manage containers

---

## Technologies Used

* Docker
* Nginx
* HTML
* WSL2 (Linux on Windows)

---

## Project Structure

```
01-nginx-docker-project/
│── Dockerfile
│── index.html
│── README.md
```

---

## Step 1: Create Project Directory

```bash
mkdir 01-nginx-docker-project
cd 01-nginx-docker-project
```

---

## Step 2: Create index.html

Create a simple HTML file that Nginx will serve.

**index.html**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Docker Nginx Project</title>
</head>
<body>
  <h1>Welcome to Nginx running inside Docker!</h1>
  <p>This is my first Docker + Nginx project.</p>
</body>
</html>
```

---

## Step 3: Create Dockerfile

The Dockerfile defines how the Docker image is built.

**Dockerfile**

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

### Dockerfile Explanation

* `FROM nginx:alpine` → Uses lightweight Nginx image
* `COPY` → Copies HTML file into Nginx web directory
* `EXPOSE 80` → Documents the container port

---

## Step 4: Build Docker Image

```bash
docker build -t 01-nginx-docker-project .
```

Check image:

```bash
docker images
```

---

## Step 5: Run Docker Container

```bash
docker run -d -p 8080:80 --name nginx-web 01-nginx-docker-project
```

### Command Explanation

* `-d` → Run container in background
* `-p 8080:80` → Host port 8080 mapped to container port 80
* `--name nginx-web` → Container name

Verify container:

```bash
docker ps
```

---

## Step 6: Access Web Application

Open browser and visit:

```
http://localhost:8080
```

You should see your HTML page.

---

## Common Errors & Fixes

### Error: Container name already exists

```text
Conflict. The container name is already in use
```

**Fix:**

```bash
docker stop nginx-web
docker rm nginx-web
```

Or use a different name:

```bash
docker run -d -p 8081:80 --name nginx-web-2 01-nginx-docker-project
```

---

## Docker Cleanup Commands

```bash
docker stop nginx-web
docker rm nginx-web
docker rmi 01-nginx-docker-project
```

---

## Final Output

* Docker image created successfully
* Nginx running inside Docker container
* Web page accessible from browser

---

## Learning Outcome

By completing this project, you learned:

* Dockerfile basics
* Image vs Container difference
* Port mapping
* Running Nginx in Docker

---

## Next Projects

* Docker Volumes
* Docker Compose
* Dockerizing Node.js application
* Jenkins with Docker

---

**Author:** DevVenkat
