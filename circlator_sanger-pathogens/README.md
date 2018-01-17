# docker-circlator_sanger-pathogens

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/circlator_sanger-pathogens/)

Docker image with [Circlator](http://sanger-pathogens.github.io/circlator/) software ([GitHub page](https://github.com/sanger-pathogens/circlator/wiki)).

**Circlator**: A tool to circularize genome assemblies

## Usage

You can download and run this image using the following commands:

```
# Get Docker image
docker pull ummidock/kraken_metagenomics:v0.10.6-unreleased

# Analyse the data with minikraken DB
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:v0.10.6-unreleased kraken --preload --fastq-input --db minikraken_20141208 --threads 2 --output /data/minikraken.sample.txt --paired --gzip-compressed /data/sample_1.fastq.gz /data/sample_2.fastq.gz

# Get Kraken report
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:v0.10.6-unreleased kraken-report --db minikraken_20141208 /data/minikraken.sample.txt > /data/minikraken.sample.report.txt
```
