## Project 1 Docker volume concept
1. Clone the repositry
   ```bash
   https://github.com/Arbazkhan04/docker_Advanced_Volume_dockerCompose_multiStageDocker.git
   ```
2. Go to docker volume folder
     ```bash
     cd dockerVolume/django-todo-cicd
     ```
3. Build images
   ```bash
   docker build -t <name of image> .
   ```
4. run the container
   ```bash
   docker run -d -p 8000:80000 <name of image>:<tag of image>
   ```
   check every thing working perfectly then roemve and kill the container
   ```bash
   docker rm <image id>
   docker kill <contaienr id>
   ```
6. Create folder outside of repo
   ```bash
   mkdir volume/django-app
   cd volume/django-app
   ```
7 copy the current path
 ```bash
   pwd
```
go back to the repo
8. Create a volume 
```bash
docker volume create --name django-todo-volume --opt type=none --opt device= pwd path(change with your volume path) --opt o=bind
```
9. run the container
   ```bash
   docker urn -d -p 8000:8000 --mount source = django-todo-volume , target = /data django-todo:latest
   ```
## Cleanup

To clean up Docker resources, you can use the following commands:

### Remove Docker volumes:

```bash
docker volume rm django-app-todo-volume
```

Remove Docker containers:
docker rm <container_id>
Remove Docker images:
docker rmi <image_id>
