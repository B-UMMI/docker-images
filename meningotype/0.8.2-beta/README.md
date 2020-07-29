# docker-meningotype

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/meningotype/)

Docker container with [meningotype](https://github.com/MDU-PHL/meningotype) software.

[**meningotype**](https://github.com/MDU-PHL/meningotype):

> In silico typing of Neisseria meningitidis contigs

> In silico serotyping, finetyping and Bexsero antigen sequence typing of Neisseria meningitidis

## Usage

You can download and run this image using the following commands:

````bash
# Pull
docker pull ummidock/meningotype:0.8.2-beta-01

# Run
docker run --rm -u $(id -u):$(id -g) -v /local/folder/data:/data/ ummidock/meningotype:0.8.2-beta-01 meningotype /data/sample.fasta
````

For more examples on how to use **meningotype** please check the [GitHub](https://github.com/MDU-PHL/meningotype) page.

## Docker file
Docker file can be found [here](https://github.com/B-UMMI/docker-images/tree/master/meningotype).

## Citation

Kwong JC, Gonçalves da Silva A, Stinear TP, Howden BP,  Seemann T.  
***meningotype*: *in silico* typing for *Neisseria meningitidis*.**  
GitHub https://github.com/MDU-PHL/meningotype
