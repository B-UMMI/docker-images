# docker-ubuntu_base

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/ubuntu_base/)

Docker image with basic Ubuntu tools.

**Tools**

* ftp
* 7zip

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/ubuntu_base:latest

    # Run
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/ubuntu_base:latest bash
