# simple-djongo-app-docker
i'm going to run a simple django application in a docker container and shared to my docker hub repository

Launch EC2 Instance with ubuntu image
![image](https://github.com/praveensivakumar1998/simple-djongo-app-docker/assets/108512714/37da191f-d530-4407-86b0-31937bf7e51c)

## Login to the Ubuntu server
`$ sudo apt update -y`

## Install docker and modify permissions to run as ubuntu user
`sudo apt install docker.io -y`
`sudo usermomd -aG docker ubuntu`
### check the docker service status is active
`sudo systemctl status docker`

NOTE: Logout to the docker machine after modify the user group to active

### Check the docker commands is run as ubuntu user
`docker run hello-world`

### Output:
`latest: Pulling from library/hello-world`
`c1ec31eb5944: Pull complete`
`Digest: sha256:4bd78111b6914a99dbc560e6a20eab57ff6655aea4a80c50b0c5491968cbc2e6`
`Status: Downloaded newer image for hello-world:latest`

`Hello from Docker!`
`This message shows that your installation appears to be working correctly.`

### clone this repository in ubuntu server

`git clone https://github.com/praveensivakumar1998/simple-djongo-app-docker.git`

### Navigate to the docker file location
`cd simple-djongo-app-docker`

### Difference between ENTRYPOINT vs CMD vs RUN ?
![image](https://github.com/praveensivakumar1998/simple-djongo-app-docker/assets/108512714/ff13dc95-309d-4ac2-ac73-e59af158a818)

CMD that can change or modify during execution or run `docker run` cmds whereas, ENTRYPOINT is couldnot able to change or modify during execution both are the actions when run on Docker run cmds

Refer this blog for more information: https://tonylixu.medium.com/docker-run-vs-cmd-vs-entrypoint-57f248b95889#:~:text=RUN%20executes%20commands%20and%20creates,docker%20run%20command%20line%20parameters.

### Now get into our learnings
## Lifecycle of Docker:
1. docker build -> builds docker images from Dockerfile
2. docker run -> runs container from docker images
3. docker push -> push the container image to public/private regestries to share the docker images.
4. docker pull -> pull the docker image from docker hub

### 1. Docker Build:
`docker build -t praveensivakumar\dockerimg1:latest .`

`-t` creating a tag for your image
`.` to specify the path for cmds to run

### output:
`Successfully built c875dd706215`
`Successfully tagged praveensivakumardockerimg1:latest`

### 2. Docker Run:
`docker run -it praveensivakumardockerimg1:latest`

`-it` tells docker that it should open an interactive container instance

### output:
`Django version 5.0.1, using settings 'devops.settings'`
`Starting development server at http://0.0.0.0:8080/`

### Now the docker container run only in the container itself 







