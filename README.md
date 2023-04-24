# homelab-containerfile

Various Containerfile for complex HomeLab configuration.

Prior knowledge of Linux and Docker/Podman is required to use this configuration. It is recommended to read documentations of [Docker](https://docs.docker.com/) or [Podman](https://docs.podman.io/en/latest/Tutorials.html) if you are not familiar with container.

## Quick Start

#### Podman

Build an image with Containerfile:

```
$ ls
Containerfile  README.md
$ podman build -t new_image .
...
```
