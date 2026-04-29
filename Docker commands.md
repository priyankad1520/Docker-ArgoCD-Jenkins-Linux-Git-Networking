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

S
