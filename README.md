# Details Buildpack

Demo [Buildpack](https://buildpacks.io/) which prints out details of the builder environment and ships `main.sh` in the workspace as the application.

# Usage (docker)

If using docker

```bash
git clone https://github.com/frayer/details-buildpack.git
cd details-buildpack
pack build test-app -B paketobuildpacks/builder:base -b ./buildpack
docker run --rm test-app
```

# Usage (podman)

If using podman

```bash
export DOCKER_HOST="unix://$(podman info -f "{{.Host.RemoteSocket.Path}}")"
git clone https://github.com/frayer/details-buildpack.git
cd details-buildpack
pack build test-app -B paketobuildpacks/builder:base -b ./buildpack --docker-host=inherit
podman run --rm test-app
```
