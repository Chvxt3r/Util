# Useful Docker Commands

## Docker
### Run a docker container and pass a command and local file
```bash
# docker run -v <current folder>:/<container folder> -w <working folder> <image name>:<image tag> <command> <local file>
docker run -v "$PWD":/app -w /app python:3.8-slim python3 exploit.py
```
