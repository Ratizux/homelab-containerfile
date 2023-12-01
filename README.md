# homelab-containerfile

Various Containerfile for complex HomeLab configuration.

Prior knowledge of Linux and Podman is required to use this configuration. It is recommended to read documentations of [Podman](https://docs.podman.io/en/latest/Tutorials.html) if you are not familiar with container.

Some configuration may not compatible with Docker.

## Quick Start

#### Build

With a Containerfile in current directory, build an image with Containerfile:

```
podman build -t new_image .
```

#### Create Container

```
podman create --name new_container new_image
```

To forward port from host to container, use `-p host:container`, like that:

```
podman create --name new_container -p 8022:22 new_image
```

Tools like `PRoot`, `gdb` and `strace` requires `ptrace()` to work. You may want to enable this capability:

```
podman create --name new_container --cap-add sys_ptrace new_image
```

You may wish KVM and/or graphics device in container:

```
podman create --name new_container --device /dev/kvm --device /dev/dri --group-add keep-groups new_image
```

#### Start Container

```
podman start new_container
```

#### Run Program

Start bash in a tty:

```
podman exec -it new_container bash
```

#### Stop Container

Stop the container:

```
podman stop new_container
```

#### Cleanup

Delete container:

```
podman rm new_container
```

Delete image:

```
podman rmi new_image
```

## Pod control

A pod can be seen as a group of containers sharing some resources, for example, network namespace.

#### Create pod

Create a new pod with ports exposed. All containers in the pod will share the network namespace (so any container listening port `80` will be exposed), please be careful of port conflicts.

```
podman pod create -p 7707:80 new_pod
```
