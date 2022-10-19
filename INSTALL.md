## Installation with Docker Image

Build image with defaults:

```bash
nvidia-docker build . -t pmtd:v1.12.0
```

Build image with `FORCE_CUDA` disabled:

```bash
nvidia-docker build . \
-t pmtd:v1.12.0 \
--build-arg FORCE_CUDA=0
```

Run image:

```bas
nvidia-docker run -it pmtd:v1.12.0 /bin/bash
```

Build and run image with built-in jupyter notebook(note that the password is used to log in jupyter notebook):

```bash
nvidia-docker build . -f Dockerfile.jupyter \
-t pmtd-jupyter:v1.12.0
```

```bash
nvidia-docker run pmtd-jupyter:v1.12.0 -td\
-p 8888:8888\
-e PASSWORD=<password>\
-v <host-dir>:<container-dir>
```