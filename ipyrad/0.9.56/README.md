# docker-ipyrad

[![dockeri.co](https://dockeri.co/image/ummidock/ipyrad)](https://hub.docker.com/r/ummidock/ipyrad)
[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/ipyrad/)

Docker container with [**ipyrad**](https://ipyrad.readthedocs.io/en/latest/) software.

[**ipyrad**](https://github.com/dereneaton/ipyrad) GitHub:

> Interactive assembly and analysis of RAD-seq data sets.

> Interactive toolkit for assembly and analysis of restriction-site associated genomic data sets (e.g., RAD, ddRAD, GBS) for population genetic and phylogenetic studies.

## Usage

You can download and run this image using the following commands:

````bash
# Pull
docker pull ummidock/ipyrad:0.9.56-01

# Run
## Create an initial Assembly params file
docker run --rm -u $(id -u):$(id -g) -v /local/folder/data:/data/ ummidock/ipyrad:0.9.56-01 sh -c 'cd /data; ipyrad -n run01'
````

For more examples on how to use **ipyrad** please check the [manual](https://ipyrad.readthedocs.io/en/latest/) page.

## Docker file
Docker file can be found [here](https://github.com/B-UMMI/docker-images/tree/master/ipyrad).

## Citation

Eaton DAR & Overcast I. "ipyrad: Interactive assembly and analysis of RADseq datasets." Bioinformatics (2020).
