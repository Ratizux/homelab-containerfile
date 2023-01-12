This is the template of a Debian Xfce4 container with VNC port on 5900.

The VNC configuration do NOT have access control or encryption.

The default configuration requires &tilde;160MiB of free RAM and 1&tilde;1.5GiB of storage, but more resource is recommended for a better experience.

# Usage

- Install `podman` or `docker`.
- Inspect the Containerfile, set your favorite username, enable what you want.
- Build the image. For example, `podman build -t xfce .`.
- Create a container. For example, `podman create -it --name al1s -p 5900:5900 xfce`.
- Use `start`, `stop`, `exec` subcommand of Podman or Docker to control the container.
