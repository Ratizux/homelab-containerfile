# Quick start

```
podman build -t chromium .
```

```
podman run --rm --device /dev/dri --group-add keep-groups -p 5900:5900 --shm-size 1G -it chromium:latest
```

# Hardware acceleration

TBD
