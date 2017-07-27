# docker-midas_metagenomics

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/midas_metagenomics/)

Docker image with [MIDAS](https://github.com/snayfach/MIDAS/) software.

**MIDAS** estimates strain-level genomic variation from metagenomic data

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/prokka:1.12

    # Estimate species abundance with MIDAS reference DB
    docker run --rm -u $(id -u):$(id -g) -it -v ~/GBS_sero_Ib_rematch:/data/ ummidock/prokka:1.12 bash

For more examples see MIDAS [GitHub](https://github.com/snayfach/MIDAS/)
