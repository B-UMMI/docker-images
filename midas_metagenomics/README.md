# docker-midas_metagenomics

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/kraken_metagenomics/)

Docker image with [MIDAS](https://github.com/snayfach/MIDAS/) software.

**MIDAS** estimates strain-level genomic variation from metagenomic data

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/midas_metagenomics:1.3.0

    # Estimate species abundance with MIDAS reference DB
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/midas_metagenomics:1.3.0 run_midas.py species /data/sample/ -1 /data/sample_1.fastq.gz -2 /data/sample_2.fastq.gz -t 2

For more examples see MIDAS [GitHub](https://github.com/snayfach/MIDAS/)
