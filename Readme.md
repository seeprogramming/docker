# Docker & Kubernetes

## Basic Commands

| Command                                | Use                                                                                                                                             | Example                                                  |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| docker build .                         | Create a docker image from the 'Dockerfile' inside project folder                                                                               | -                                                        |
| docker run -p port:port image_id       | Use the image_id generated from `docker build .` command to run the container                                                                   | docker run -p 3000:3000 c1ae0f4d8dd7                     |
| docker ps                              | List all running docker containers / processes (`ps - processes`)                                                                               |                                                          |
| docker stop container_name             | Stop the docker container using the name of the container                                                                                       | docker stop laughing_taussig                             |
| docker ps -a                           | Lists all containers                                                                                                                            |                                                          |
| docker run -it image_name              | Run container in interactive mode (`it - interactive`). After running this command node will run inside this container no in our local machines | docker run -it node                                      |
| docker ps --help                       | Lists all command related option                                                                                                                | docker ps -a --help                                      |
| docker run containerId                 | Runs docker in attached mode                                                                                                                    | docker start lucid_robinson                              |
| docker start containerId               | Starts docker in detached mode                                                                                                                  | docker run -p 8000:80 72b446e12c                         |
| docker logs containerName              | view logs                                                                                                                                       | docker logs epic_ptolemy                                 |
| docker logs -f containerName           | View logs contineously in attached mode                                                                                                         | docker logs -f epic_ptolemy                              |
| docker attach containerName            | Attach a started container to view logs contineously in attached mode                                                                           | docker attach epic_ptolemy                               |
| docker rm container1,container2        | Removes the specified containers                                                                                                                | docker rm laughing_taussig epic_blackwell amazing_mclean |
| docker images                          | To view all images                                                                                                                              | docker images                                            |
| docker rmi imageId                     | Delete specific image                                                                                                                           | docker rmi 1ccdd95065ec                                  |
| docker run -p port -d --rm containerId | removes container after being stopped                                                                                                           | docker run -p 3000:80 -d --rm 1c7f4cb9788                |
| docker image inspect imageId           | inspected the docker image                                                                                                                      | docker image inspect 1c7f4cb9788b                        |

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
