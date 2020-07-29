FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="2.53-01"

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && \
    apt-get install -y wget g++ zlib1g-dev make

# Stacks
RUN wget http://catchenlab.life.illinois.edu/stacks/source/stacks-2.53.tar.gz && \
    tar xf stacks-2.53.tar.gz && \
    rm stacks-2.53.tar.gz && \
    cd stacks-2.53 && \
    ./configure && \
    make && \
    make install && \
    make clean

# Clean
RUN apt-get remove -y wget g++ make && \
    apt-get autoclean -y

WORKDIR /data/

# Default command
CMD denovo_map.pl -h
