# Containerisation with Docker

## What is Docker
- Docker is an open-source platform for developing, shipping, and running applications
- It enables us to separate applications from the infrastructure
- It delivers software faster
- Docker is written in GO language

![docker](docker.png)

## Docker vs VM 
- Docker is lightweight and user-friendly
- Docker shares the resources of OS as opposed to using the OS completely
- Docker engine connects the container with the OS and only uses the resources required
- VM works with Hypervisor to connect guest OS/VM with Host OS

![container-vs-vm](container-vs-vm.png)

# Docker commands
- `Docker images`: Will present the images available
- `Docker ps`: To check the containers running
- `Docker ps -a`: To check every container running including hidden files
- `Docker pull`: to pull the image from docker hub
- `Docker run` : to run the image live directly from dockerhub
- `docker exec` -it [container id] bash: to access the running container
- `docker stop`: stops a running container
- `docker kill`: kills container by stopping execution. stop gives time to shut down gracefully
- `docker commit` [container id][username/imagename]: creates new image of an edited container on local system
- `docker rm [container id]`:removes container 
- `docker history [image name]`: to view history 
- `docker image rm [image name]`: deletes image 

#### Making docker docs available on our localhost 

```
docker run -d -p 4000:4000 docs/docker.github.io 
```

#### Logging into a running container 

```
docker exec -it <container-id/name> sh

```
#### Port mapping in our containers with localhost 
```
docker run -d -p localhost-port:container-port

```
#### Copying files to container 
```
docker cp <file to copy> <container_id>:path/to/file

```
#### Running a container with ghost
```
docker run -d -p 2368:2368 ghost 
```

#### Running nginx on port 80 
```
docker run -d -p 80:80 nginx 
```
#### Replacing nginx default page 

```
docker cp index.html a4700feaa1c0:/usr/share/nginx/html
```
#### Commit to save changes to image, then push to dockerhub 
```
# docker commit <container_id> brittanyharrison/repo_name
docker push brittanyharrison/repo_name

```
**Note**:Repository name and local folder name must match
