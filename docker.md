### Docs 
* Command line interface https://docs.docker.com/engine/reference/commandline/cli/

### Data volumes 

* https://docs.docker.com/engine/userguide/dockervolumes/

### Official packages

* https://hub.docker.com/_/httpd/
* https://hub.docker.com/_/nginx/
* https://hub.docker.com/_/elasticsearch/

* https://hub.docker.com/r/million12/varnish/


### Selected Tuto

* https://www.digitalocean.com/community/tutorials/docker-explained-using-dockerfiles-to-automate-building-of-images
* Example docker file For httpd image
https://github.com/docker-library/httpd/blob/master/2.4/Dockerfile
* https://coreos.com/os/docs/latest/getting-started-with-docker.html

### How to 

#### List active docker containers

```docker ps -l```

Output 
````
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                           NAMES
00bb4123c87d        nginx               "nginx -g 'daemon off"   57 minutes ago      Up 57 minutes       0.0.0.0:32769->80/tcp, 0.0.0.0:32768->443/tcp   mysite
````
#### Connect to an ubuntu image 

docker run -t -i ubuntu /bin/bash

#### a container port to the machine port 

````docker run -d -p 80:80 coreos/apache /usr/sbin/apache2ctl -D FOREGROUND````
with -p 80:80 we map the docker port to the host machine port

#### List all docker images on the local machine 
````docker images````

It give a display like this
````
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
<none>              <none>              4a8042f24167        5 minutes ago       223.8 MB
slucas/apache       latest              bd868a91e83b        26 minutes ago      223.8 MB
<none>              <none>              67b63fb2ba48        33 minutes ago      209.4 MB
myapache21          latest              3086f6c31b58        20 hours ago        193.5 MB
myapache2           latest              9eed1ba5f77f        20 hours ago        193.5 MB
ubuntu              latest              c4bea91afef3        40 hours ago        187.9 MB
````

### Push a docker image to the docker hub 
````
docker login
 docker push [userName]/[imageName]
````

### Fix some commons mac installation docker problem 

* https://docs.docker.com/engine/installation/mac/

### List container open ports
* docker port 05d3b3c3c685
80/tcp -> 0.0.0.0:80

### Run and build a docker image 

#### First build the container
```docker build -t my-apache2 .````
* docker command
* build docker command 
* -t option to give a name : my-apache2
-t, --tag=                      Repository name (and optionally a tag) for the image
* . read the content of a docker file in the current directory

#### Then run it 
```docker run --name=apache -i -t my-apache2``` 
* docker command
* run docker command 
* --name=apache option to set the name of the container (the running container,not the saved image)

> docker run + the image name you would like to run + the command to run within the container

>  It's important to note that containers are designed to stop once the command executed within them has exited. For example, if you ran /bin/echo hello world as your command, the container will start, print hello world and then stop:

### Docker files 

* https://docs.docker.com/engine/articles/dockerfile_best-practices/#run

### Image linking 

* https://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/