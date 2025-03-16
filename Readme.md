# Docker & Kubernetes

## Basic Commands

| Command                            | Use                                                                             | Example                              |
| ---------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------ |
| docker build .                     | Create a docker image from the 'Dockerfile' inside project folder               | -                                    |
| docker run -p port:port <image_id> | Use the <image_id> generated from `docker build .` command to run the container | docker run -p 3000:3000 c1ae0f4d8dd7 |
| docker ps                          | List all docker containers                                                      |                                      |
| docker stop <container_name>       | Stop the docker container using the name of the container                       | docker stop <laughing_taussig>       |
