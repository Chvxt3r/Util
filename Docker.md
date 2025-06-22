# Useful Docker Commands

## Docker
### Containers
* List running containers
  ```bash
  docker ps -a
  ```
* Remove containers
  ```bash
  docker rm <container ID>
  ```
* Remove all containers
  ```bash
  docker rm $(docker ps -a -q)
  ```
### Images
* List images
  ```bash
  docker images ls
  ```
* Remove Images
  ```bash
  docker images rm <image name>:<image tag>
  ```
### Run a docker container and pass a command and local file
```bash
# docker run -v <current folder>:/<container folder> -w <working folder> <image name>:<image tag> <command> <local file>
docker run -v "$PWD":/app -w /app python:3.8-slim python3 exploit.py
```
