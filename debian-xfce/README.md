Template of Debian Xfce4 container with:

- Xfce4 Desktop Environment
- VNC on port 5900 (Note: No access control or encryption enabled)

# Requirements

- Make sure you have `docker` or `podman` installed
- At least 200MiB of available RAM, or 1GiB for a better experience
- At least 1.5GiB of available disk space

# Usage

### Inspect Containerfile

- Set custom username, uncomment lines to enable additional features.

### Build

- With Podman, use `podman build -t IMAGE_NAME .`
    - You may have to rename `Containerfile` to `Dockerfile` to build with Docker. After that, run `docker build -t IMAGE_NAME .`

### Create

- With Podman, use `podman create -it --name CONTAINER_NAME -p 5900:5900 IMAGE_NAME`
    - Specify `--net host` if you prefer host sharing network with container. Use `podman create -it --name CONTAINER_NAME --net host IMAGE_NAME`

### Examples

- With Podman:
    - `podman start CONTAINER_NAME`
    - `podman stop CONTAINER_NAME`
    - `podman exec -it COMMAND CONTAINER_NAME`
