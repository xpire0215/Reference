# Make a web server in Docker

### Make a directory

```
> make devops-web
> cd devops-web
```

### Write a Dockerfile

```
> vim Dockerfile

(Dockerfile)
FROM httpd:2.4
## This copy the directory into the container
## If the image is built, it can't reflect the modification in www, you should rebuild it
# COPY ./www/ /usr/local/apache2/htdocs/
```

### Make a www directory

```
> make www
```

### Write a start script

```
> vim start.sh

(start.sh)
#!/bin/bash

## Build the image with Dockerfile
# docker build -t web-server .

## Run the container in the background which is built from image web-server
## Pass the traffic from port 8080 on localhost to port 80 on container
## Pass the directory www to the container (realtime)
docker run -dit --name web-server-app -p 8080:80 -v "$PWD/www":/usr/local/apache2/htdocs/ web-server
```

### Configuration

To customize the configuration of the httpd server, first obtain the upstream default configuration from the container:

```
$ docker run --rm httpd:2.4 cat /usr/local/apache2/conf/httpd.conf > my-httpd.conf
```