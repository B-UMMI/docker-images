# docker-blast+

Docker container with a [Blast+](https://blast.ncbi.nlm.nih.gov/Blast.cgi) software binaries.  
For LOBO cluster performance testing **ONLY**.

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/bionode-ncbi/)

Usage
-----

    shifterimg pull ummidock/blast_binaries:2.6.0-binaries
    shifter --image=ummidock/blast_binaries:2.6.0-binaries blastn -help
