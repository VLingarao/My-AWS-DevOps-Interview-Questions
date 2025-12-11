# **Docker On EC2  (Open Source Containerisation Platform, Docker Alternate Tool: Rocketd)**

------------------ **Day -1** ------------------

**1. yum install docker -y** * -->(Install Docker package into EC2 automatically without asking for confirmation)*

**2. systemctl start docker** * -->(Start Docker service)*

**3. systemctl enable docker** * -->(Enable Docker auto-start on system reboot)*

**4. systemctl status docker** * -->(Check Docker service is running or not)*

**5. docker --version** * -->(Shows installed Docker version)*

**6. docker version  -->(it will give the client and server)** *(Displays detailed client & server Docker version)*

**7. docker default path is /var/lib/docker** * -->(Location where Docker stores images, containers, layers)*

**8. docker pull nginx  -->(it will go to docker hub registry image, next time it will on check the docker file it will give the quick)** * -->(Downloads nginx image from Docker Hub registry)*

**9. docker images  -->(it will give the list off docker images in your ec2)** *(Displays all downloaded Docker images)*

**10. docker run nginx  -->(container will run)** *(Runs nginx container in foreground mode)*

**11. if control + c  -->(stops the container)** *(Ctrl+C stops foreground running container)*

**12. docker run -dt nginx** * -->(Runs container in detached mode (-d) with terminal (-t))*

**13. docker ps  -->(give the list off running containers)** *(Shows only running containers)*

**14. docker ps -a  -->(it will show the both running and stopped containers )** *(Shows all containers including stopped ones)*

**15. docker ps -a | grep exited  -->(give the exited containers list)** *(Filters only exited/stopped containers)*

**16. docker run -dt -p 81:80 nginx  -->(this docker run on this port number ex : -p <localhostport>:<targetcontainer> nginx)**
* -->(Maps EC2 port 81 → container port 80, run nginx)*

**17. ec2 public ip  -->(3.87.10.80):81  -->(give the broser default nginx page)**
* -->(Access nginx webpage using EC2 public IP on mapped port)*

**18. if you done ec2 Nginx installing it will give the Nginx default Page**
* -->(EC2-installed nginx also gives same default page)*

**19. if docker run -dt -p 80:80 nginx  -->(it will through the error if run docker on ec2 exapet docker don't run any other on ec2)**
* -->(Port conflict occurs because EC2 already using port 80)*

**20. docker pull ubuntu  -->(it will install the docker hub img base os img)**
* -->(Downloads Ubuntu base OS image)*

**21. docker run -it ubuntu /bin/bash  -->(run a continer on go inside container)**
* -->(Run Ubuntu container and open interactive bash shell)*

**22. ls  -->(give the list off)** * -->(List files inside container)*

**23. ps -ef  -->(give the number of prosses on running)** *(Shows running processes inside container)*

**24. ps -ef | wc -l** * -->(Counts number of running processes)*

**25. exit** * -->(Exit from container terminal)*

**26. now run ps -ef  -->(so many prosses are running) and ps -ef | wc -l  -->(138)**
* -->(EC2 has many processes compared to container)*

**27. control + p + q** * -->(Detach from container without stopping it)*

**28. docker pull httpd** * -->(Download Apache HTTP server image)*

**29. docker run -dt -p 87:80 httpd** * -->(Run Apache server on port 87)*

**30. docker logs id** * -->(Get logs of container using container ID)*

------------------ **Day -2** ------------------

**31. cat etc/** * -->(List content of /etc directory)*

**32. sudo usermod -a -G docker ec2-user  -->(add user into Docker Group || if you run docker pull nginx on ec2-user get permission denied)**
* -->(Add ec2-user to docker group so it can run Docker without sudo)*

**33. newgrp docker** * -->(Refresh group membership so new Docker permissions apply)*

**34. docker inspect nginx** * -->(Shows detailed metadata of nginx image)*

**35. docker run -it -p 81:80 nginx /bin/bash** * -->(Run nginx container and enter bash shell with port mapping)*

**36. control + p + q  -->(<-- is not kill the container) -->(exit command is kill)**
* -->(Detach without stopping, exit command kills the session)*

**37. docker exec -it a823bc1971142 -->(container ID)  -->(-->  )**
* -->(Access a running container shell)*

**38. docker pull Jenkins/Jenkins** * -->(Download Jenkins official Docker image)*

**39. docker run -dt -p 8081:8080 Jenkins/Jenkins  -->(Jenkins install on docker container )  -->(for password refer 37 point)**
* -->(Run Jenkins container, access with port 8081, password inside container logs)*

**40. docker rm conID -f** * -->(Force remove a container)*

**41. docker stop conId after 40** * -->(Stop container — but here container already removed so not required)*

**42. docker container prune  -->(delt all container stopd only)**
* -->(Delete only stopped containers)*

**43. docker rm -f $ -->(docker ps -aq)  -->(delete al running and stoped all)**
* -->(Force delete all containers: running + stopped)*

**44. docker rmi nginx** * -->(Remove nginx image from EC2)*

Below is the **clean, correct, production-style workflow**, covering only:

### **Stage-1 to Stage-7**

and

### **A sample Flask Dockerfile** (professional, working version)

This is the exact process you follow **after creating a new EC2 instance** and **installing Docker**.

---

# **------ Day-3 (Docker_Python_Flask Project) ----------

---
# **STAGE-1: Connect to EC2**
1. **ssh -i key.pem ec2-user@Public_IP**
   (Connect to your EC2 instance.)
---
# **STAGE-2: Install Docker (Already Done)**

You already ran:
```
* yum install docker -y
* systemctl start docker
* systemctl enable docker
```
Continue below.

---

# **STAGE-3: Add EC2 User to Docker Group**

This prevents “permission denied” errors.

2. **sudo usermod -aG docker ec2-user**
3. **logout**
4. **ssh into EC2 again**

(Now docker commands work without sudo.)

---

# **STAGE-4: Get Your Flask Project on EC2**

You must bring your Flask project code to the server.

### Option A: Clone from GitHub (recommended)

5. **sudo yum install git -y**
6. **git clone https://github.com/VLingarao/docker_flaskapp.git**
7. **cd flaskapp**

### Option B: Create a small test Flask project

Use if you don’t have code.

5.

```
mkdir flaskapp
cd flaskapp
```

6. Create files:

```
touch app.py
touch requirements.txt
touch Dockerfile
```

7. Add basic Flask code into app.py:

```
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "Flask Docker app running successfully!"

if __name__ == "__main__":
    app.run(host="0.0.0.0")
```

8. requirements.txt:

```
Flask
```

---

# **STAGE-5: Build Docker Image**

Move into your project folder where Dockerfile exists.

9. **docker build -t flaskapp .**
   (Example: creates image with the name flaskapp)

Explanation:
Reads your Dockerfile and builds a Docker image.

---

# **STAGE-6: Run the Container**

10. **docker run -dt -p 5000:5000 flaskapp**

Explanation:

* Runs the image named flaskapp
* Exposes port 5000
* Starts Flask server inside Docker
* -d = detached mode

Open in browser:
**http://EC2_Public_IP:5000**

---

# **STAGE-7: Manage / Debug the Running Container**

Use these commands after the container is running:

### 11. **docker exec -it containerID /bin/bash**

(Enter the container terminal)

### 12. **docker logs containerID**

(View Flask logs)

### 13. **docker inspect flaskapp**

(See full metadata of your image)

---

# **STAGE-1 to STAGE-7 Final Order (Clean Summary)**

1. ssh into EC2
2. Install Docker
3. Add docker group
4. Upload or create Flask project
5. cd flaskapp
6. docker build -t flaskapp .
7. docker run -dt -p 5000:5000 flaskapp
8. docker exec -it containerID /bin/bash
9. docker logs containerID
10. docker inspect flaskapp

(These cover all your commands required for Docker + Flask deployment.)

---

# **SAMPLE DOCKERFILE (Flask Production-Ready)**

Place this as **Dockerfile** in your project folder.

```
# Use official Python base image
FROM python:3.9-slim

# Set working directory inside container
WORKDIR /app

# Copy requirement file
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy project files into container
COPY . .

# Expose Flask port
EXPOSE 5000

# Command to run the Flask app
CMD ["python", "app.py"]
```

This Dockerfile is perfect for any Flask project.

---
