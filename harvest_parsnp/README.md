# docker-harvest_parsnp

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/harvest_parsnp/)

Docker image with [_Harvest_](https://harvest.readthedocs.io/en/latest/index.html) **Parsnp** software ([Read th Docs page](https://harvest.readthedocs.io/en/latest/content/parsnp.html)).

**Parsnp**
> "Parsnp was designed to align the core genome of hundreds to thousands of bacterial genomes within a few minutes to few hours". From [here](https://harvest.readthedocs.io/en/latest/content/parsnp.html).

---

## Usage

You can download and run this image using the following commands:
```bash
# Get Docker image
docker pull ummidock/harvest_parsnp:1.2-01

# Run Parsnp
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/harvest_parsnp:1.2-01 parsnp –p 8 –d /data/assemblies/ –r /data/reference.fasta -o /data/output_dir/
```

---

## Image Content

This Docker image contains:
* [Parsnp](https://harvest.readthedocs.io/en/latest/content/parsnp.html) v1.2
