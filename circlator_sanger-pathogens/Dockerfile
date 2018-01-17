FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget bzip2 make gcc zlib1g-dev && \
    wget https://downloads.sourceforge.net/project/bio-bwa/bwa-0.7.17.tar.bz2 && tar xf bwa-0.7.17.tar.bz2 && rm bwa-0.7.17.tar.bz2 && cd bwa-0.7.17 && make && rm *.h *.o *.c *.1 && cd /NGStools && \
    mkdir Prodigal_v2.6.3 && cd Prodigal_v2.6.3 && wget https://github.com/hyattpd/Prodigal/releases/download/v2.6.3/prodigal.linux && mv prodigal.linux prodigal && chmod +x prodigal && cd /NGStools

ENV PATH="/NGStools/Prodigal_v2.6.3:/NGStools/bwa-0.7.17:${PATH}"

RUN apt-get remove -y wget bzip2 make gcc && \
    apt-get autoclean -y

WORKDIR /data/
