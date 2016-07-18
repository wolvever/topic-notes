LearnDocker
====================

# Commands

## Run containers

* `docker run <image-name>`
* `docker run -t -i <image-name> <command>`
	* `-t` Allocate a pseudo tty
	* `-i` Keep stdin open
	* `-p` <container-port>:<host-port> Map container port to host
	* `-d` Run docker in background
	* `--name <container-name>` Name container
	* `-link <container-name>` Links another container by name
* `docker run -it -v /$(pwd):/home/test -P ubuntu /bin/bash`
	* `-v <path-to-host-dir>:<path-to-container-dir>:rw` Add volumn

## Container start & stop

* Start container & attach to bash:	`docker start -a -i <container-id>`
* Stop container:					          `docker stop <container-id>`
* Copy file to container: 		    	`docker cp <file-path> <container-id>:<container-file-path>`
* Attach to a background container: `docker attach <container-id>`

## Cleanup

* Remove a container: 				    `docker rm <Container ID>`
* Remove last created container:	`docker rm $(docker ps -q -l)`
* Remove all containers: 			    `docker rm $(docker ps -a -q)`
* Remove images:				        	`docker rmi <Container ID>`
* Remove untagged images:			    `docker rmi $(docker images --filter "dangling=true" -q)`
* Remove all images: 			      	`docker rmi $(docker images -q)`

## Inspect containers

* Changes made to container:	`docker diff <container-id>`
* Get container detail:			  `docker inspect <container-id>`
* Last created container:		  `docker ps -q -l`
* List all images: 			    	`docker images`
* List untagged images:		  	`docker images --filter "dangling=true"`

## Get IP

* `docker inspect fbb9390ff2ce | jq ".[0].NetworkSettings.Networks.bridge.IPAddress"`
* `docker-machine ip default`

## Dockerfile
* `FROM <image-id:version>`		      	image base
* `RUN <cmd>`							            sh -c <cmd> as root user
* `ADD <host-file> <container-file>`	copy file from host to container
* `EXPOSE <port1> <port2> ...`		    expose a port to host machine
* `CMD ["<cmd>"]`					          	run a command without (sh -c)
* `ENV k="v"`							            setup environment variables

## Build docker image

* Build current directory image with tag:	`docker build -t bps/kafka:0.9 .`
* Tag a image:							            	`docker tag <image-id> <name>:<tag>`

## Docker-machine

* List all machines:  `docker-machine ls`
* Create new machine: `docker-machine -d docker <machine-name>`


# References

* [Architecture](https://docs.docker.com/v1.8/introduction/understanding-docker/)
* [Images, containers and storage drivers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)
* [Command line guide](https://docs.docker.com/engine/reference/commandline/	)
* [Dockerfile guide](https://docs.docker.com/engine/reference/builder/)
* [Composefile guide](https://docs.docker.com/compose/compose-file/)
* [Data volumnes](https://docs.docker.com/engine/tutorials/dockervolumes/)
* [Docker swarm get started](https://docs.docker.com/swarm/install-w-machine/)

## Security

* [Authentication and authorization](https://docs.docker.com/engine/extend/plugins_authorization/)
* [Swarm TLS deploy](https://docs.docker.com/swarm/configure-tls/)
* [Get started](https://serversforhackers.com/getting-started-with-docker)

## Kafka dockers

* [Kafka docker by wurstmeister](https://github.com/wurstmeister/kafka-docker)
* [Kafka docker by spotify](https://github.com/spotify/docker-kafka)
* [Kafka docker by ches](https://github.com/ches/docker-kafka/blob/master/start.sh)
* [Understand docker volumn](http://container-solutions.com/understanding-volumes-docker/)
