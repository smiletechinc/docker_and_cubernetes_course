# Create a unility container

## Create image for docker
```
docker build -t mynpm
```

## Run docker container
```
docker run -it -v "$(pwd):/app" mynpm
```