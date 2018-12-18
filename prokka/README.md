# docker-prokka

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/prokka/)

Docker image with [Prokka](https://github.com/tseemann/prokka) software.

**Prokka** annotates bacterial, archaeal and viral genomes  
Due to licences permissions, this image does not contain:
* [SignalP](http://www.cbs.dtu.dk/services/SignalP/) (used to find signal peptide features in CDS)
  * `--gram` option cannot be used
* [RNAmmer](http://www.cbs.dtu.dk/services/RNAmmer/) (used to find ribosomal RNA features)
  * It uses [Barrnap](https://github.com/tseemann/barrnap) for rRNA prediction
  * `--rnammer` option cannot be used

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/prokka:1.13.3-01

    # Wizard annotation
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/prokka:1.13.3-01 prokka --outdir /data/SAMPLE/ --force --addgenes --centre UMMI --compliant --genus Streptococcus --species agalactiae --strain SAMPLE --cpus 2 --rfam --prefix SAMPLE --locustag SAMPLEp --increment 10 /data/sample.fasta

For more examples see Prokka [GitHub](https://github.com/tseemann/prokka)
