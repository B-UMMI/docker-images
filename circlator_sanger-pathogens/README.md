# docker-circlator_sanger-pathogens

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/circlator_sanger-pathogens/)

Docker image with [Circlator](http://sanger-pathogens.github.io/circlator/) software ([GitHub page](https://github.com/sanger-pathogens/circlator/wiki)).

**Circlator**: A tool to circularize genome assemblies

## Usage

You can download and run this image using the following commands:

```
# Get Docker image
docker pull ummidock/circlator_sanger-pathogens:v1.5.3

# Run Circlator
## Given an assembly assembly.fasta in FASTA format and corrected PacBio reads in a file called reads, run
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/circlator_sanger-pathogens:v1.5.3 circlator all /data/assembly.fasta /data/reads /data/circlator_output/
```
For more examples see Circlator [GitHub](https://github.com/sanger-pathogens/circlator/wiki)

## Image Content

This Docker image contains:
* [Circlator](http://sanger-pathogens.github.io/circlator/) v1.5.3
* [BWA](http://bio-bwa.sourceforge.net/) v0.7.17
* [Prodigal](https://github.com/hyattpd/Prodigal) v2.6.3
* [Samtools](http://www.htslib.org/) v1.3.1
* [MUMmer](https://github.com/mummer4/mummer) v4.0.0beta2
* [SPAdes](http://cab.spbu.ru/software/spades/) v3.11.1
* [Canu](http://canu.readthedocs.io/en/latest/) v1.6
