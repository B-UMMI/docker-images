# docker-spades

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/spades/)

Docker image with [SPAdes](https://cab.spbu.ru/software/spades/) software.

**SPAdes** – St. Petersburg genome assembler – is an assembly toolkit containing various assembly pipelines. 

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/spades:3.12.0-0.1

    # Assemble the data with SPAdes
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/spades:3.12.0-0.1  spades.py -o /data/<output_dir> -1 /data/sample_1.fastq.gz -2 /data/sample_2.fastq.gz

  