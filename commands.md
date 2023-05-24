# Docker Commands 


## IMAGES
- Downloading Images
```
docker pull <image name>
```
- List all images
```
docker images -a
```
- Delete single Image
```
docker rmi <image id>
```
- Deleting all images
```
docker rmi $(docker images  -q)
```
- Dangling images delete(Dangling images are layers that have no relationship to any tagged images. They no longer serve a purpose and consume disk space)
```
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
```



## CONTAINERS
- Creating a interactive container  from image
```
docker run -it <image name>
```
- Giving a name to a container while creating
```
docker run --name <container name> -it <image name>
```
- Starting a stopped Container
```
docker start (container_id)
```
- Stop all containers
```
sudo docker kill $(sudo docker ps -a) or ctrl+ D
```
- Connect shell to running container
```
docker exec -it (container_id) bash
```
- Delete a single Container
```
docker rm <container id or container name>
```
- Delete all containers
```
docker rm $(docker ps -a -q)
```
## Building Image from Docker File
- Terminal from same directory
```
docker built -t <image name > .
```

## GUI arguments
### Windows

## Complete Examples
- Running a container with GUI enabled for Windows
```
docker run -it --name <container_name> -e DISPLAY=host.docker.internal:0.0 -e <image_name> bash

```

