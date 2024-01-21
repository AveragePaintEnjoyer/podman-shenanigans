# podman-shenanigans

## general

### podman x xorg

How to run gui applications inside podman containers.

1. Build image with app installed

```bash
cd to/directory/with/dockerfile
podman build --tag ghcr.io/averagepaintenjoyer/image_name:tag .
```

2. Run container

```bash
podman run --rm -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --security-opt label=type:container_runtime_t image_name
```

## images

### podman-firefox

- run firefox-browser in podman container
- image is based on fedora

### podman-polymc

- run polymc in podman container
- be able to play minecraft inside podman
- image is based on fedora