
## Instructions
- Fork and Clone :  `https://github.com/ActuaryEmma/yolo`
- Change in to yolo directory : `cd yolo`
- Run docker compose to install the image and create a container : `sudo docker compose up --build`
- Backend runs on port `5000` and Frontend runs on port `3000`
- Push images to docker hub : sudo docker compose push
- The README has instructions that you can run the application  without `docker-compose.yml` and `Dockerfile` and locally.
- Go ahead a nd add a product (note that the price field only takes a numeric input) 


## Docker file
- FROM : Initializes the build stage and sets the base image as `node:19-alpine3.15` since its a light weight and fast image

- WORKDIR /app : changes the current working directory from / to /app

- COPY package*.json ./ : Copies the package.json and add them to the file system of the container at that path

- RUN npm install, RUN npm run build, RUN npm install -g serve : execute any command in a new layer on top of the current image and commits the results during build execution.

- COPY . . : copy the files from the Docker host to the filesystem of the new image
 
- EXPOSE : Indicates to Docker that the container will have a process listening on the given port or ports (api : `5000`, client : `3000`)

- CMD [ "serve", "-s", "build", "-l", "3000" ] : Excecuted when the container is launched from the newly created image.

## Docker Compose
- define and share multi container applications.
  Version : This is the version of the docker compose
  Services : Has 3 services - `api, backend and mongo`
  Each servive has an image and container that builds when you run `sudo docker compose up --build`
  Networks: There is a custom network `yolo_mynetwork`
  
  

## Docker Hub links
[Yolo Frontend](https://hub.docker.com/repository/docker/actuaryemma/frontend)
[Yolo Backend](https://hub.docker.com/repository/docker/actuaryemma/api)
