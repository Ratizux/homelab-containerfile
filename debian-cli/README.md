Debian container with essential command-line tools, providing a plain experience.

The default configuration requires &tilde;20MiB of free RAM and &tilde;560MiB of storage, but more resource is recommended for a better experience.

# Usage

- Install `podman` or `docker`.
- Inspect the Containerfile, set your favorite username, enable what you want.
- Build the image. For example, `podman build -t cli .`.
- Create a container. For example, `podman create -it --name al1s -p 8022:22 cli`.
- Use `start`, `stop`, `exec` subcommand of Podman or Docker to control the container.
