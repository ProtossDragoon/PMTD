## Installation with Docker Image

Build image with defaults (`CUDA=9.0`, `CUDNN=7`, `FORCE_CUDA=1`):

```bash
nvidia-docker build . -t pmtd
```
    
Build image with other CUDA and CUDNN versions:

```bash
nvidia-docker build .\
-t pmtd \
--build-arg CUDA=9.2\
--build-arg CUDNN=7
```
    
Build image with `FORCE_CUDA` disabled:

```bash
nvidia-docker build .\
-t pmtd \
--build-arg FORCE_CUDA=0
```
    
Build and run image with built-in jupyter notebook(note that the password is used to log in jupyter notebook):

```bash
nvidia-docker build . -f Dockerfile.jupyter\
-t pmtd-jupyter
```

```bash
nvidia-docker run pmtd-jupyter -td\
-p 8888:8888\
-e PASSWORD=<password>\
-v <host-dir>:<container-dir>
```