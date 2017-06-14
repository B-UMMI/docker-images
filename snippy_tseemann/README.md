# docker-snippy_tseemann

Docker container with [Snippy](https://github.com/tseemann/snippy) software.

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/bionode-ncbi/)

Usage
-----

You can download and run this image using the following commands:

    docker pull ummidock/snippy_tseemann:3.1
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/snippy_tseemann:3.1 snippy --cpus 1 --cleanup --outdir /data/sample/ --ref /data/ref.gbk --pe1 /data/sample_1.fastq.gz --pe2 /data/sample_2.fastq.gz
