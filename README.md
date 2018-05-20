## Follow the guide to install docker: 
https://blog.alexellis.io/getting-started-with-docker-on-raspberry-pi/

TLDR: 
1. curl -sSL https://get.docker.com | sh

2. Set Docker to auto-start
```
$ sudo systemctl enable docker
```
You can now reboot the Pi, or start the Docker daemon with: 
```
$ sudo systemctl start docker
```

3. Enable Docker client
The Docker client can only be used by root or members of the docker group.

4. Add pi or your equivalent user to the docker group:
```
$ sudo usermod -aG docker pi
```
## installing postgres container

```
docker pull arm32v7/postgres
docker run --name pi-postgres -e POSTGRES_PASSWORD=mysecretpassword -d arm32v7/postgres
```

Some useful commands:
https://medium.com/statuscode/dockercheatsheet-9730ce03630d
```
docker version
docker images
docker ls

docker search
docker pull
docker build
```
## creating a swarm
https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/
```
docker info
docker swarm init
docker swarm join
docker swarm join-token worker
docker node ls

```

docker build -t dummypage .
docker run --name dummycontainer -p 8080:80 dummypage

docker rmi dummypage --force
docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)