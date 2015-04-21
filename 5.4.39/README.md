## Debian Dockerfile

This repository contains **Dockerfile** of [Nginx](http://nginx.org/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/julienvincent/nginx/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* [debian:wheezy](https://registry.hub.docker.com/u/alexisvincent/debian/)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/julienvincent/nginx/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull julienvincent/nginx`

   (alternatively, you can build an image from Dockerfile: `docker build -t="julienvincent/nginx" github.com/julienvincent/docker-nginx`)


### Usage

    docker run -it --rm julienvincent/nginx
