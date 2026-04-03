## Jenkins Installation on VM

To run Jenkins in Docker with access to the host Docker daemon, use:

```bash
docker run -d \
  --name jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $(which docker):/usr/bin/docker \
  -u root \
  -e DOCKER_GID=$(getent group docker | cut -d: -f3) \
  jenkins/jenkins:lts-jdk21
```

## Jenkins Installation on Docker Desktop

To run Jenkins in Docker with access to the host Docker daemon, use:

```bash
docker run -d ^
  --name jenkins ^
  -p 8080:8080 ^
  -p 50000:50000 ^
  -v //var/run/docker.sock:/var/run/docker.sock ^
  -u root ^
  jenkins/jenkins:lts-jdk21
```
