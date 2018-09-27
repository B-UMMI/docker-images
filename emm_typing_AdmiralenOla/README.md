# docker-emm_typing_AdmiralenOla

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/emm_typing_AdmiralenOla/)

Docker image with **emm_typing** software ([GitHub page](https://github.com/AdmiralenOla/emm_typing)).

**emm_typing**
> "Typing of the emm gene of Streptococcus pyogenes (and other Streptococci)". From [here](https://github.com/AdmiralenOla/emm_typing/blob/master/setup.py).

---

## Usage

You can download and run this image using the following commands:
```bash
# Get Docker image
docker pull ummidock/emm_typing_AdmiralenOla:0.4-01

# Run emm_typing with default DB
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/emm_typing_AdmiralenOla:0.4-01 emm_typing --outdir /data/output_dir/ --fasta /data/sample_1.fasta /data/sample_2.fasta
```

---

## Image Content

This Docker image contains:
* [Blast](https://blast.ncbi.nlm.nih.gov/Blast.cgi) v2.2.31+
