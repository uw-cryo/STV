# STV Docker Image with key software:
[![build-and-push](https://github.com/uw-cryo/STV/actions/workflows/build-docker-image.yml/badge.svg)](https://github.com/uw-cryo/STV/actions/workflows/build-docker-image.yml)

* Conda 

* JupyterLab 3

* DART 5.8.12
https://dart.omp.eu

* Ames Stereo Pipeline 3.1.0
https://stereopipeline.readthedocs.io/en/latest/index.html

* QGIS 3.22.11
https://www.qgis.org/en/site/

## Run locally
```
docker run -it --rm ghcr.io/uw-cryo/stv:latest /bin/bash
```

## Instructions for building locally
```
docker buildx build -f https://raw.githubusercontent.com/scottyhq/pangeo-buildx/main/Dockerfile ./ -t ghcr.io/uw-cryo/stv:2022.10.19
```

To push to GitHub Packages you first need to authenticate with an access token (https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry#authenticating-to-the-container-registry)
```
export CR_PAT=YOUR_TOKEN
echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
docker push ghcr.io/uw-cryo/stv:2022.10.19
```
