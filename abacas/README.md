# docker-abacas

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/abacas/)

Docker image with [ABACAS](http://abacas.sourceforge.net/index.html) software.

**ABACAS** is intended to rapidly contiguate (align, order, orientate) assembled contigs based on a reference sequence.

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/abacas:1.3.1

    #
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/abacas:1.3.1
