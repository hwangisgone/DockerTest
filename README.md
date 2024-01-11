### Build the docker image 
### At the directory with Dockerfile
```
sudo docker build -t landing-page . --no-cache
```
### Run the docker image
```
sudo docker run -p 5000:3000 landing-page
```
### See all running docker images
```
sudo docker ps
sudo docker stop <CONTAINER ID>
```