# Docker Operation

### Search Image, [--no-trunc] show full description

```
> docker search image\_name
```

### Search Image tag

Use curl or go to docker hub search

### Get Image, [image_name:tag] specify the tag 

```
> docker pull image_name
```

### Run image with tty and create container

[-i] interactive, Keep STDIN open even if not attached

[-t] tty, Allocate a pseudo-TTY

[-d] detach, Run container in background and print container ID

```
> docker run -i -t ubuntu
```

### Show images

```
> docker image ls -a
```

### Show containers

```
> docker ps -a

> docker container ls -a
```

### Delete image

```
> docker rmi image_id
```

### Delete container

```
> docker rm container_id
```

### Start container

```
> docker container start container_name
```

### Stop container

```
> docker container stop container_name
```

### Publish a new image

```
> docker commit -m "message" -a "publisher_name" 
container_id new_image_name:image_tag
```

## Error response "daemon: conflict"

### First, remove the container with name or id

```
> docker rm container_name

> docker rm container_id
```

### Second, remove the image

```
> docker rmi image_name

> docker rmi image_id
```

## Error response from daemon: conflict: unable to delete image_id (must be forced) - image is referenced in multiple repositories

```
> docker rmi -f image_id
```