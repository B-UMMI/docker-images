# docker-blast+

Docker container with a [Blast+](https://blast.ncbi.nlm.nih.gov/Blast.cgi) software built from source for LOBO cluster architecture (INTEL Broadwell).

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/bionode-ncbi/)

Usage
-----

You can download and run this image using the following commands:

    docker pull miguelpmachado/blast:2.6.0-broadwell
    docker run -it -v /local/folder/data:/container_data miguelpmachado/blast/2.6.0-broadwell bash


In LOBO cluster context:

    shifterimg pull miguelpmachado/blast:2.6.0-broadwell
    shifter --image=miguelpmachado/blast:2.6.0-broadwell blastn -help
