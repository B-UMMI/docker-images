# docker-abricate

Docker container with a [abricate](https://github.com/tseemann/abricate) software.

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/abricate/)

Usage
-----

```bash
# Using with Docker
## Get image
docker pull ummidock/abricate:latest
## Docker usage
docker run --rm ummidock/abricate:latest abricate --list
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data/:/data/ ummidock/abricate:latest abricate --db resfinder /data/sequence.*.fasta > /local/folder/data/abricate_out.resfinder.tab
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data/:/data/ ummidock/abricate:latest abricate --summary /data/abricate_out.resfinder.tab > /local/folder/data/abricate_summary.resfinder.tab

# Using with Shifter (containers for HPC)
shifterimg pull ummidock/abricate:latest
shifter --image=ummidock/abricate:latest abricate --help
```
