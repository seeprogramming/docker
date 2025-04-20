Dockerize BOTH apps - the Python and the Node app.

1. Create appropriate images for both apps (two separate images!).
   HINT: Have a brief look at the app code to configure your images correctly!

2. Launch a container for each created image, making sure,
   that the app inside the container works correctly and is usable.

3. Re-create both containers and assign names to both containers.
   Use these names to stop and restart both containers.

4. Clean up (remove) all stopped (and running) containers,
   clean up all created images.

5. Re-build the images - this time with names and tags assigned to them.

6. Run new containers based on the re-built images, ensuring that the containers
   are removed automatically when stopped.

### My Solution ::

TASK 1 :: Create appropriate images for both apps (two separate images!).

`node-app`

App is simply showing a text and is running on port 3000

Create a dockerfile

```dockerfile
FROM node

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 3000

CMD ["node", "server.js"]
```

Run below command to create a image after creating dockerfile

```sh
docker build .
```

Run the container using image

```sh
docker run -p 3000:3000 imageid
```

`python-app`
