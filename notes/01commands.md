### to list all the iamges 
docker image ls -a

### to list all the containers
docker ps -a

### to remove containers
docker rm -f dd5b17779d9b b3113eeefc13

### to remove a single image
first run `docker images` to grab the id
then run `docker rmi <image_id>`

### to remove all the images

`docker rmi $(docker images -a -q)`

`docker images -a -q` lists all image IDs (including those not currently associated with any containers).

`docker rmi` is used to remove the images.

The command first lists all image IDs and then passes them to `docker rmi` for removal. This will will permanently delete all images, and they cannot be recovered.

