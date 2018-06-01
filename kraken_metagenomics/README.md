# docker-kraken_metagenomics

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/kraken_metagenomics/)

Docker image with [Kraken](https://ccb.jhu.edu/software/kraken/) software.

**Kraken** assigns taxonomic labels to short DNA sequences, usually obtained by metagenomic studies

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/kraken_metagenomics:v0.10.6-unreleased

    # Analyse the data with minikraken DB
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:v0.10.6-unreleased kraken --preload --fastq-input --db minikraken_20141208 --threads 2 --output /data/minikraken.sample.txt --paired --gzip-compressed /data/sample_1.fastq.gz /data/sample_2.fastq.gz

    # Get Kraken report
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:v0.10.6-unreleased kraken-report --db minikraken_20141208 /data/minikraken.sample.txt > /local/folder/data/minikraken.sample.report.txt
