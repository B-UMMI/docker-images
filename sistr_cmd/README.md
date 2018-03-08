# docker-sistr_cmd

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/sistr_cmd/)

Docker image with [SISTR](https://lfz.corefacility.ca/sistr-app/) command line software ([GitHub page](https://github.com/peterk87/sistr_cmd)).

**SISTR**: Salmonella serovar predictions from whole-genome sequence assemblies

## Usage

You can download and run this image using the following commands:

```
# Get Docker image
docker pull ummidock/sistr_cmd:1.0.2

# Run sistr_cmd
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/sistr_cmd:1.0.2 sistr --qc -vv --alleles-output /data/allele-results.json --novel-alleles /data/novel-alleles.fasta --cgmlst-profiles /data/cgmlst-profiles.csv -f tab -o /data/sistr-output.tab /data/assembly.fasta
```

## Image Content

This Docker image contains:
* sistr_cmd
* Blast+
* MAFFT
* Mash
