# Basic Docker Image Creation

This is just a simple node app which works specifically on node 14.

```plaintext

FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "app.mjs"]

```

## Build an image

```plaintext

docker build .

```

## Start container with image_id

```plaintext

docker run -p 3000:3000 <image_id>

Ex:: docker run -p 3000:3000 c1ae0f4d8dd7

```

## Check all running containers

```plaintext

docker ps

```

### Output

| CONTAINER ID | IMAGE        | COMMAND                | CREATED        | STATUS       | PORTS                  | NAMES          |
| ------------ | ------------ | ---------------------- | -------------- | ------------ | ---------------------- | -------------- |
| 785e94ca8573 | c1ae0f4d8dd7 | "docker-entrypoint.s…" | 10 seconds ago | Up 9 seconds | 0.0.0.0:3000->3000/tcp | epic_blackwell |

## Stop docker container

```plaintext

docker stop <container_name>

Ex:: docker stop <laughing_taussig>

```
