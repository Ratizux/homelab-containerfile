# homelab-containerfile

Various Containerfile for complex HomeLab configuration.

Prior knowledge of Linux and Docker/Podman is required to use this configuration. It is recommended to read documentations of [Docker](https://docs.docker.com/) or [Podman](https://docs.podman.io/en/latest/Tutorials.html) if you are not familiar with container.

## Quick Start

#### Podman

With a Containerfile in current directory, build an image with Containerfile:

```
podman build -t new_image .
```

And create a container:

```
podman create --name new_container new_image
```

&nbsp;&nbsp;&nbsp;&nbsp;Or if you want to bind port `8022` on the host to `22` in the container:
    
```
    podman create --name new_container -p 8022:22 new_image
```

&nbsp;&nbsp;&nbsp;&nbsp;With `ptrace()`:

```
    podman create --name new_container --cap-add sys_ptrace new_image
```

&nbsp;&nbsp;&nbsp;&nbsp;With `/dev/kvm` passed through:

```
    podman create --name new_container --device /dev/kvm --group-add keep-groups new_image
```

Start the container:

```
podman start new_container
```

You may want to execute a program in a running container:

```
podman exec -it new_container bash
```

&nbsp;&nbsp;&nbsp;&nbsp;Or without a tty:

```
    podman exec new_container ls
```

Stop the container:

```
podman stop new_container
```

Delete image:

```
podman rm new_image
```
