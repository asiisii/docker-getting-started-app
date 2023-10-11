#### step1: run below command to build an image
`docker build -t getting-started .`

<!-- 
The `docker build` command uses the Dockerfile to build a new image 
`-t getting-started` this basically gives a name to the image
The `.` at the end of the` docker build` command tells Docker that it should look for the `Dockerfile` in the current directory.
-->

#### step2: run below command to start an app container
`docker run -dp 127.0.0.1:3000:3000 getting-started`

The `-d` flag (short for --detach) runs the container in the background. The `-p` flag (short for --publish) creates a port mapping between the host and the container. 
The `-p` flag takes a string value in the format of `HOST:CONTAINER`, where `HOST` is the address on the host, and `CONTAINER` is the port on the container. 
The command publishes the container's port 3000 to `127.0.0.1:3000` (`localhost:3000`) on the host. 

Without the port mapping, we wouldn't be able to access the application from the host.

#### step2: run below command in a terminal to list containers
`docker ps` 

output should look like this
CONTAINER ID   IMAGE             COMMAND                  CREATED         STATUS         PORTS                      NAMES
5a3cc71b6876   getting-started   "docker-entrypoint.s…"   6 minutes ago   Up 5 minutes   127.0.0.1:3000->3000/tcp   vibrant_kirch