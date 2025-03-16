# Docker & Kubernetes

## Basic Commands

| Command                            | Use                                                                             | Example                              |
| ---------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------ |
| docker build .                     | Create a docker image from the 'Dockerfile' inside project folder               | -                                    |
| docker run -p port:port <image_id> | Use the <image_id> generated from `docker build .` command to run the container | docker run -p 3000:3000 c1ae0f4d8dd7 |
| docker ps                          | List all docker containers                                                      |                                      |
| docker stop <container_name>       | Stop the docker container using the name of the container                       | docker stop <laughing_taussig>       |

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
