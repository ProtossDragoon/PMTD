# Installation with Docker Image

## Hardware

NVIDIA GPU (support CUDA >= 11)

## Default container

### Build image  
```bash
nvidia-docker build . -t pmtd:v1.12.0
```

### Run image
```bash
nvidia-docker run \
-it \
--mount type=bind,source="$(pwd)"/output,target=/PMTD/output \
pmtd:v1.12.0 /bin/bash
```

## Jupyter notebook container

### Build image
```bash
nvidia-docker build . -f Dockerfile.jupyter \
-t pmtd-jupyter:v1.12.0
```

### Run image (note that the password is used to log in jupyter notebook)
```bash
nvidia-docker run pmtd-jupyter:v1.12.0 -td \
-p 8888:8888 \
-e PASSWORD=<password> \
--mount type=bind,source="$(pwd)"/output,target=/PMTD/output
```