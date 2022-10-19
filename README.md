# pangeo-buildx-template
[![build-and-push](https://github.com/scottyhq/pangeo-buildx-template/actions/workflows/build-docker-image.yml/badge.svg)](https://github.com/scottyhq/pangeo-buildx-template/actions/workflows/build-docker-image.yml)

template for quickly creating public docker images


## Usage:

1. Click use this template
1. Update this README.md if you want (status badge etc to point to *your* image)
1. Customize environment by adding [repo2docker files](https://repo2docker.readthedocs.io/en/latest/config_files.html)
1. Use resulting image pushed to GitHub Packages!

## BinderHub Usage
To use your built image on mybinder.org just put a Dockerfile in a separate repository pointing to your image and corresponding tag (usually this is a github short "sha"):
```
FROM ghcr.io/scottyhq/pangeo-buildx-template:0f1b90c
```

If you want to automatically pull content into a BinderHub session use https://jupyterhub.github.io/nbgitpuller/index.html


## How does this work?
The github action in this repository points to a Dockerfile in https://github.com/scottyhq/pangeo-buildx that expects certain configuration files such as the conda environment.yml to build a Docker image for you.
