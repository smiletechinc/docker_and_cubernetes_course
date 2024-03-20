# API Documentation for Node.js App

## Run node app by running
    ```
    node server.js
    ```

## Build docker image
    ```
    docker build -t node-volume-image:volumes
    ```

## run the above create build
    ```
    docker run -p 3002:80 --name node-volume-container --rm -v feedback:/app/feedback -v "/Users/hfsmacbook/Development/Docker and Kubernetes Course/data-volumes-01-starting-setup":/app -v app/node_modules node-volume-image:volumes
    ```
    OR
    ```
    docker run -p 3002:80 --name node-volume-container --rm -v feedback:/app/feedback -v "$(pwd):/app" -v app/node_modules node-volume-image:volumes
    ```

## Run with .env file in project
    ```
    docker run -p 3003:8000 --env-file ./.env --name node-volume-container --rm -v feedback:/app/feedback -v "$(pwd):/app" -v app/node_modules node-volume-image:env
    ```

## Accessible urls/apis/routes

| Sr. No. | Route       |
|---------|-------------|
| 1.      | `/`         | 
| 2.      | `/exists`   |
| 3.      | `/create`   |
| 4.      | `/feedback` |

## Provide feedback

    Provide feedback by adding title and description in the input boxes

## Access file from url
    ```
    http://localhost:3000/feedback/file.txt
    ```
    Where `file` is coming from the title from the feedback