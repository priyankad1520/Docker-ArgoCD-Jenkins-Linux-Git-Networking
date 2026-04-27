# Docker Commands

Some of the most commonly used docker commands are 

1. docker images: Lists docker images on the host machine.

2. docker build: Builds image from Dockerfile.

3. docker run: Runs a Docker container. 

There are many arguments which you can pass to this command for example,

`docker run -d` -> Run container in background and print container ID
`docker run -p` -> Port mapping

use `docker run --help` to look into more arguments.

4. docker ps: Lists running containers on the host machine.

5. docker stop: Stops running container.

6. docker start: Starts a stopped container.

7. docker rm: Removes a stopped container.

8. docker rmi: Removes an image from the host machine.

9. docker pull: Downloads an image from the configured registry.

10. docker push: Uploads an image to the configured registry.

11. docker exec: Run a command in a running container.

12. docker network: Manage Docker networks such as creating and removing networks, and connecting containers to networks.
Here are **commonly used Docker commands in one-line format** (simple and interview-friendly):

---

###  Basic Docker Commands

* `docker --version` → Check Docker version
* `docker info` → Display system-wide info
* `docker help` → List all commands

---

###  Image Commands

* `docker pull <image_name>` → Download image from Docker Hub
* `docker images` → List all images
* `docker rmi <image_id>` → Remove image
* `docker build -t <image_name> .` → Build image from Dockerfile

---

###  Container Commands

* `docker run <image_name>` → Run container
* `docker run -d <image_name>` → Run container in background
* `docker run -it <image_name> /bin/bash` → Interactive mode
* `docker ps` → List running containers
* `docker ps -a` → List all containers
* `docker stop <container_id>` → Stop container
* `docker start <container_id>` → Start container
* `docker restart <container_id>` → Restart container
* `docker rm <container_id>` → Remove container

---

###  Logs & Exec Commands

* `docker logs <container_id>` → View logs
* `docker exec -it <container_id> /bin/bash` → Enter running container

---

###  Networking Commands

* `docker network ls` → List networks
* `docker network create <network_name>` → Create network

---

###  Volume Commands

* `docker volume ls` → List volumes
* `docker volume create <volume_name>` → Create volume

---

###  System Cleanup

* `docker system prune` → Remove unused data
* `docker container prune` → Remove stopped containers

---

###  Docker Hub Commands

* `docker login` → Login to Docker Hub
* `docker push <image_name>` → Upload image
* `docker pull <image_name>` → Download image

---
Good choice 👍 Let’s go with **real-time DevOps Docker commands (practical usage)** — this is what interviewers expect.

---

##  Real-Time Docker Commands (DevOps Use Cases)

####  1. Run Application Container with Port Mapping
Runs Nginx in background and maps container port 80 to server port 80
```bash
docker run -d -p 80:80 nginx
```
---
####  2. Run Container with Custom Name
Assigns a readable name instead of container ID
```bash
docker run -d --name myapp nginx
```
---
####  3. Restart Policy (Important in Production)
Container auto-restarts if it crashes or server reboots
```bash
docker run -d --restart=always nginx
```
---
####  4. Mount Volume (Persistent Storage)
Data will not be lost even if container stops
```bash
docker run -d -v /host/data:/container/data nginx
```
---
####  5. Pass Environment Variables
Used for configuration like DB credentials
```bash
docker run -d -e ENV=prod nginx
```
---
###  6. Check Logs for Debugging
Real-time logs (very important in troubleshooting)
```bash
docker logs -f <container_id>
```
---
####  7. Execute Command Inside Container
Access running container (like SSH)
```bash
docker exec -it <container_id> /bin/bash
```
---
####  8. Clean Up Unused Resources
Removes unused images, containers, networks
```bash
docker system prune -a
```
---
####  9. Build Image from Dockerfile
Used in CI/CD pipelines
```bash
docker build -t myapp:v1 .
```
---
####  10. Push Image to Docker Hub
Share image with team or deployment
```bash
docker push myrepo/myapp:v1
```
---
####  11. Pull Image from Registry
Used in deployment servers
```bash
docker pull myrepo/myapp:v1
```
---
####  12. Create Custom Network
Allows container-to-container communication
```bash
docker network create mynetwork
```
---
####  13. Run Container in Custom Network
```bash
docker run -d --network=mynetwork nginx
```
---
####  14. Check Resource Usage
CPU, memory usage (monitoring)
```bash
docker stats
```
---
####  15. Inspect Container Details
Full JSON details (IP, config, mounts)
```bash
docker inspect <container_id>
```
---

👉 *"How do you debug a failed container?"*

You can answer:

1. `docker ps -a`
2. `docker logs <id>`
3. `docker inspect <id>`
4. `docker exec -it <id> /bin/bash`

## **Dockerfile – all important instructions in order**
#### 1. FROM: Defines the base image (starting point) 
Why: Every image needs a foundation (like OS or runtime) 
* `FROM ubuntu:20.04` → Base image
---
####  2. LABEL: Adds metadata to image / Adds info about image (owner, version)
Why: Helps in documentation and management 
* `LABEL maintainer="priyanka@example.com"` → Metadata
---
####  3. ENV: Sets environment variables 
Why: Used for configuration inside container (like config values)
* `ENV APP_ENV=production` → Set environment variable
---
#### 4. ARG:  Build-time variable. 
Why: Used during image build only (not runtime) /  Pass values during image build (`docker build --build-arg`)
* `ARG VERSION=1.0` → Build-time variable
---
#### 5. WORKDIR: Sets working directory inside container 
Why: Avoid writing full paths again and again

What actually happens when you use WORKDIR?
WORKDIR = "cd + mkdir (if needed)" automatically. Inside container image WORKDIR /app
* `WORKDIR /app` → Set working directory. What it does: Sets /app as the current working directory inside the container  All next commands (RUN, CMD, COPY) will run inside /app
* If /app does NOT exist → Docker will automatically create it. If /app already exists → Docker will just use it. So you don’t need to create it manually.
* 


What happens and how its work:
```
Start container from Ubuntu image 
WORKDIR /app #Docker checks: does /app exist?  No → creates /app 
COPY . . # copies into /app
RUN touch file.txt #File created inside /app or runs inside /app
Final path: /app/file.txt
```

Multiple WORKDIR example: Docker builds nested directories automatically
```
WORKDIR /app
WORKDIR logs
WORKDIR today
Result: /app → created, /app/logs → created, /app/logs/today → created 
```
Important Behavior:  Relative vs Absolute path
```
WORKDIR /app
WORKDIR test
Result: /app/test
```
- How to access WORKDIR: Inside container: docker exec -it container_name bash --->  cd /app
-	WORKDIR sets working directory inside container 
-	Automatically creates directory if not exists 
-	Supports relative paths 
-	Affects RUN, CMD, COPY, ENTRYPOINT 
- Cleaner than using cd in RUN 
---
####  6. COPY: Copies files from local to container 
Why: Used to move / add application code into image 
* `COPY . /app` → Copy files from local to container
* First, we clone the GitHub repository to local or CI server. Then we navigate to the project directory and build the Docker image using docker build. Docker requires local build context to copy files into the image.
* Clone repo → go inside folder → build image
* If you are working manually (your laptop): Yes, you must clone the repo
* If you are using CI/CD (Jenkins, GitHub Actions):  You don’t clone manually. But system automatically clones
* Yes, we usually clone the repository before building the Docker image because Docker requires a local build context. In CI/CD pipelines, the cloning is handled automatically by tools like Jenkins.
* Flow: Developer pushes code → GitHub Jenkins triggers pipeline
* Jenkins does:
```
git clone repo
cd project
docker build -t myapp .
docker push myapp
``` 
---
####  7. ADD: Similar to COPY but supports URL & auto-extract 
Why: Useful for downloading or extracting files / Advanced copy (but mostly avoid, use COPY)
* `ADD app.tar.gz /app` → Copy + auto-extract / URL support
---
####  8. RUN: Executes commands during image build 
Why: Used to install packages/ software or setup environment and dependencies. To prepare the image
* `RUN apt update && apt install -y python3` → Execute command at build time
---
####  9. EXPOSE: Defines port used by container 
Why: Inform which port app runs on (not actually publish) /Helps in communication (documentation purpose) 
* `EXPOSE 8080` → Declare port
---
####  10. VOLUME: Creates mount point for persistent data 
Why: Persist data outside container/ Data is not lost when container is removed 
* `VOLUME /data` → Create mount point
---
#### 11. USER: Specifies user to run container 
Why: Improves security (avoid root user) 
* `USER appuser` → Run container as specific user
---
#### 12. CMD: Default command to run when container starts 
Why: Tells container what to execute at runtime / Runs when container starts (can override)
* `CMD ["python3", "app.py"]` → Runs python app.py and Starts your application/ Default command
Always run: Main application, Server process (Starts Nginx web server), Long-running process
``` docker run myapp ```
Docker does: Creates container --> Starts container and Executes CMD instruction
---
#### 13. ENTRYPOINT: Sets main command (like fixed executable) 
Why: Ensures container always runs specific command / Makes container behave like executable
* `ENTRYPOINT ["python3"]` → Fixed main command
---
#### 14. HEALTHCHECK: Why: Check container health status
* `HEALTHCHECK CMD curl --fail http://localhost:8080 || exit 1`
---
#### 15. ONBUILD: Executes instruction when image is used as base 
Why: Used for reusable base images
* `ONBUILD COPY . /app` → Trigger when used as base image
---

## Full Example Dockerfile (Real Scenario)

```dockerfile
FROM python:3.9
LABEL maintainer="priyanka@example.com"
ENV APP_ENV=production
WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
```

---

### Simple Order to Remember
**FROM → LABEL → ARG → ENV → WORKDIR → COPY/ADD → RUN → EXPOSE → VOLUME → USER → CMD/ENTRYPOINT**
---
### Important Tips
* Use `COPY` instead of `ADD` (best practice)
* Combine `RUN` commands to reduce layers
* Use `CMD` for default, `ENTRYPOINT` for fixed command
* Keep image size small (use slim/alpine images)

---



