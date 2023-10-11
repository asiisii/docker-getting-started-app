#### Step 1: Update the code from src/static/js/app.js
`- <p className="text-center">No items yet! Add one above!</p>
+ <p className="text-center">You have no todo items yet! Add one above!</p>`

#### Step 2: Build the updated version of the image
`docker build -t getting-started .`

#### Step 3: Start up the container
`docker run -dp 127.0.0.1:3000:3000 getting-started`

The error occurred because you aren't able to start the new container while your old container is still running. 
The reason is that the old container is already using the host's port 3000 and only one process on the machine 
(containers included) can listen to a specific port. To fix this, you need to remove the old container.

#### Step 4: To get the container id
`docker ps`

#### Step 5: to stop and remove a container in a single command by adding the force flag to the `docker rm` command
`docker rm -f <the-container-id>`

#### Step 6: re-run the container
`docker run -dp 127.0.0.1:3000:3000 getting-started`

#### Step 7: Referesh the page with port 3000 to see the udpated page

