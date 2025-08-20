# Quick start

Build image:

```
podman build -t flatpak-runtime .
```

Create container:

```
podman run --device /dev/dri --group-add keep-groups --name flatpak --rm -p 5900:5900 --shm-size 1G --security-opt unmask=ALL -it flatpak-runtime
```

`--security-opt unmask=ALL` is required for Bubblewrap to mount `/proc`.

In case of any problem, check SELinux/AppArmor settings and/or add `--security-opt apparmor=unconfined --security-opt seccomp=unconfined` and try again.

# Install flatpak applications

`flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`

`flatpak remote-modify --user flathub --url=https://mirror.sjtu.edu.cn/flathub`

`flatpak install --user com.valvesoftware.Steam`

# Hardware acceleration

TBD
