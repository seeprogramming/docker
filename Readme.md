# Docker & Kubernetes

## Basic Commands

| Command                                                                  | Use                                                                                                                                                                                                                                                                                                                        | Example                                                                                           |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| docker build .                                                           | Create a docker image from the 'Dockerfile' inside project folder                                                                                                                                                                                                                                                          | -                                                                                                 |
| docker run -p port:port image_id                                         | Use the image_id generated from `docker build .` command to run the container                                                                                                                                                                                                                                              | docker run -p 3000:80 c1ae0f4d8dd7                                                                |
| docker ps                                                                | List all running docker containers / processes (`ps - processes`)                                                                                                                                                                                                                                                          |                                                                                                   |
| docker stop container_name                                               | Stop the docker container using the name of the container                                                                                                                                                                                                                                                                  | docker stop laughing_taussig                                                                      |
| docker ps -a                                                             | Lists all containers                                                                                                                                                                                                                                                                                                       |                                                                                                   |
| docker run -it image_name                                                | Run container in interactive mode (`it - interactive`). After running this command node will run inside this container no in our local machines                                                                                                                                                                            | docker run -it node                                                                               |
| docker ps --help                                                         | Lists all command related option                                                                                                                                                                                                                                                                                           | docker ps -a --help                                                                               |
| docker run containerId                                                   | Runs docker in attached mode                                                                                                                                                                                                                                                                                               | docker start lucid_robinson                                                                       |
| docker start containerId                                                 | Starts docker in detached mode                                                                                                                                                                                                                                                                                             | docker run -p 8000:80 72b446e12c                                                                  |
| docker logs containerName                                                | view logs                                                                                                                                                                                                                                                                                                                  | docker logs epic_ptolemy                                                                          |
| docker logs -f containerName                                             | View logs contineously in attached mode                                                                                                                                                                                                                                                                                    | docker logs -f epic_ptolemy                                                                       |
| docker attach containerName                                              | Attach a started container to view logs contineously in attached mode                                                                                                                                                                                                                                                      | docker attach epic_ptolemy                                                                        |
| docker rm container1,container2                                          | Removes the specified containers                                                                                                                                                                                                                                                                                           | docker rm laughing_taussig epic_blackwell amazing_mclean                                          |
| docker images                                                            | To view all images                                                                                                                                                                                                                                                                                                         | docker images                                                                                     |
| docker rmi imageId                                                       | Delete specific image                                                                                                                                                                                                                                                                                                      | docker rmi 1ccdd95065ec                                                                           |
| docker run -p port -d --rm containerId                                   | removes container after being stopped                                                                                                                                                                                                                                                                                      | docker run -p 3000:80 -d --rm 1c7f4cb9788                                                         |
| docker image inspect imageId                                             | inspected the docker image                                                                                                                                                                                                                                                                                                 | docker image inspect 1c7f4cb9788b                                                                 |
| docker cp localpath containerId:/path                                    | Copying files into container                                                                                                                                                                                                                                                                                               | docker cp dummy/. mystifying_pike:/test                                                           |
| docker cp containerId:/path localpath                                    | Copying files from container to local                                                                                                                                                                                                                                                                                      | docker cp mystifying_pike:/test/text.txt dummy                                                    |
| docker run -p 3000:80 -d --rm --name containerName imageId               | Give a custome name to a container                                                                                                                                                                                                                                                                                         | docker run -p 3000:80 -d --rm --name goalsapp 2cc001395023                                        |
| docker build -t name:tag .                                               | Tagging a image                                                                                                                                                                                                                                                                                                            | docker build -t goals:latest .                                                                    |
| docker tag imageId:tag dockerhubId and docker push dockerhubId           | Push your images to docker hub. First create a dockerhub account, create a repository, tag your existing repo with same a repo id of docker hub, then do login using cli and then push                                                                                                                                     | docker tag nodeapp:latest shaggy356/node-hello-world and docker push shaggy356/node-hello-world   |
| docker image prune -a                                                    | Deletes all the images                                                                                                                                                                                                                                                                                                     | docker image prune -a                                                                             |
| docker pull imageId (as per docker hub)                                  | Pull published image                                                                                                                                                                                                                                                                                                       | docker pull shaggy356/node-hello-world                                                            |
| docker volume ls                                                         | Check the docker volumes                                                                                                                                                                                                                                                                                                   | docker volume ls                                                                                  |
| docker run -d -p 3000:80 --rm --name appName -v volumeName:path name:tag | This Docker command runs a container named feedback-app in detached mode (-d), mapping port 3000 on the host to port 80 inside the container. It uses the image feedback-node:volumes, mounts a named volume feedback to /app/feedback inside the container, and automatically removes the container when it stops (--rm). | docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes |

## 🖼️ **What is a Docker Image?**

-   A **blueprint** for creating containers.
-   Contains **Node.js**, your app code, and dependencies.
-   **Cannot run** on its own.

## 📦 **What is a Docker Container?**

-   A **running instance** of a Docker image.
-   Can start, stop, or delete it anytime.
-   Runs your **Node.js app** inside an isolated environment.

## 🖥️ **Diagram: Docker Image vs Container**

```
📦 Image (Blueprint)
├── App Code
├── Libraries
├── Dependencies
└── OS (optional)

🚀 Container (Running Instance)
├── Image + Read/Write Layer
├── Running Processes
├── Network & Storage
└── Unique Container ID
```

## 🔥 **Key Differences**

| Feature         | Image (📦) | Container (🚀) |
| --------------- | ---------- | -------------- |
| **What is it?** | A template | A running app  |
| **State**       | Read-only  | Read-Write     |
| **Runs?**       | ❌ No      | ✅ Yes         |
| **Changes?**    | Fixed      | Can change     |

---

## 🏗 **Example: Node.js App in Docker**

```sh
# Step 1: Pull a Node.js image
docker pull node

# Step 2: Create and run a container
docker run -it node bash

# Inside the container, check Node.js version
node -v
```

## Running the external images

```sh

docker run node

```

This command will download and run the latest node images from [Docker Hub](https://hub.docker.com/)

## Catalogue

| App                         | Location                                   |     |
| --------------------------- | ------------------------------------------ | --- |
| Basic docker image creation | [Basic](./first-demo-starting-setup/)      |     |
| NodeJS app image creation   | [NodeJS App](./nodejs-app-starting-setup/) |     |
