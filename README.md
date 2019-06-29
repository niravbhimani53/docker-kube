#### Docker start container_id
```
  Docker run = Docker create + Docker start
```

#### Stop container and forcefully kill after 10 seconds

`Docker stop containter_id`

#### Without waiting kill container

`Docker kill containter_id`


#### Docker run extra command inside container. Can use exec/run

`docker exec -it container_id command`

#### Interacting with container command propmt

` docker exec -it container_id sh||bash||zsh||powershell`

#### Build Dockerfile using 

`docker build .`

. specify the build context or directory save location


#### Tagging the Docker Image (From Dockerfile)

`docker_id / name : version`

Also instead of specifying docker_id, passing name will work


#### Port Mapping

exporting port outside container 

`docker run -p 8080:8080 image_name`

#### Docker compose

New build `docker-compose up`. 

When change are made to file system run `docker-compose up --build`

By adding `-d` flag, container will start in background and keep on running


```
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyhello" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
```

#### Dev and Production enviroment
Production  -> Dockerfile
Development -> Dockerfile.dev (Custom file extension name used for dev env)
Command to run custom docker file `docker build -f Dockerfile.dev .`


#### Docker volumes 
Connect local file to docker container files location. Files will sync as there are updated.

`docker build -p 3000:3000 -v /app/node_modules -v $(pwd):/location_of_folder_in_docker image_id`


#### To run test in docker container
`docker run image_id npm run test`























