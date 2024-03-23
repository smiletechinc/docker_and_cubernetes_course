## Create a docker network
Run the following command to create a docker network
```
docker network create mern_docker_network
```
## Dockerize mongo
Run the following command to run a docker container
```
docker run -v data:/data/db -e MONGO_INITDB_ROOT_USERNAME=hfshan247 -e MONGO_INITDB_ROOT_PASSWORD=Password123 --name mern_mongo_container --network mern_docker_network --rm mongo
```
OR Without auth 
```
```
docker run -v data:/data/db --name mern_mongo_container --network mern_docker_network --rm mongo

## Create image for backend
Run the following command in backend directory to create a backend image
```
docker build -t mern_backend_image .
```

## Dockerize backend
Run the following command in backend directory to run a docker container
```
docker run -p 8080:8080 -e MONGO_INITDB_ROOT_USERNAME=hfshan247 -e MONGO_INITDB_ROOT_PASSWORD=Password123 --name mern_backend_container --network mern_docker_network --rm mern_backend_image
```
OR Without auth
```
docker run -p 8080:8080 --name mern_backend_container --network mern_docker_network -v logs:/app/logs -v "$(pwd):/app" -v /app/node_modules --rm mern_backend_image
```
## Create image for frontend
Run the following command in frontend directory to create a frontend image
```
docker build -t mern_frontend_image .
```

## Dockerize frontend
Run the following command in frontend directory to run docker container
```
docker run -p 3000:3000 -it --name mern_frontend_container --network mern_docker_network -v "$(pwd):/app/src" --rm mern_frontend_image
```

