## 1. [Install docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

## 2. Build the docker image 
### At the directory with Dockerfile
```
sudo docker build -t landing-page . --no-cache
```
## 3. Run the docker image
```
sudo docker run -p 5000:3000 landing-page
```
## 4. See all running docker images
```
sudo docker ps
sudo docker stop <CONTAINER ID>
```