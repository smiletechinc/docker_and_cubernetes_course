# Node and Mongo db

## Create a network
Run the following command to create a network
```
docker network create node-network
```

## Run docker container for mongodb in the above network
Run the following command to run a mongo db container inside the network
```
docker run --name mongodb_container --network mongo-node-network --rm mongo
```

## Change default mongo db url:
Change url  
```
mongodb://localhost:27017/swfavorites
```
to  
```
mongodb://host.docker.internal:27017/swfavorites
```

## Build the latest image for node app
Run the following command to create a build for the node js app
```
 docker build -t node_networks_image .
```

## Run docker container for nodejs app in the above network
Run the following command to run a mongo db container inside the network
```
docker run -p 3000:3000 --name node_networks_container --network mongo-node-network --rm node_networks_image
```
