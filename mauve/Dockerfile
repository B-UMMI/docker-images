FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
# Java
RUN apt-get install -y default-jre wget tar

# Mauve
RUN wget http://darlinglab.org/mauve/snapshots/2015/2015-02-13/linux-x64/mauve_linux_snapshot_2015-02-13.tar.gz && tar xf mauve_linux_snapshot_2015-02-13.tar.gz && rm mauve_linux_snapshot_2015-02-13.tar.gz
ENV PATH="/NGStools/mauve_snapshot_2015-02-13:/NGStools/mauve_snapshot_2015-02-13/linux-x64:${PATH}"
# Create executable for Reordering contigs from the command-line
RUN echo '#!/bin/bash' > /NGStools/mauve_snapshot_2015-02-13/mauve_contigOrderer && echo 'java -Xmx500m -cp /NGStools/mauve_snapshot_2015-02-13/Mauve.jar org.gel.mauve.contigs.ContigOrderer $@' >> /NGStools/mauve_snapshot_2015-02-13/mauve_contigOrderer && chmod +x /NGStools/mauve_snapshot_2015-02-13/mauve_contigOrderer

# Clean
RUN apt-get remove -y wget && apt-get autoclean -y

WORKDIR /data/
