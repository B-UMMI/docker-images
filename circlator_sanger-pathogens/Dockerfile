FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

# Dependencies

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget bzip2 make g++ zlib1g-dev libncurses5-dev python3

RUN wget https://downloads.sourceforge.net/project/bio-bwa/bwa-0.7.17.tar.bz2 && \
    tar xf bwa-0.7.17.tar.bz2 && \
    rm bwa-0.7.17.tar.bz2 && \
    cd bwa-0.7.17 && \
    make && \
    rm *.o && \
    cd /NGStools

RUN mkdir Prodigal_v2.6.3 && \
    cd Prodigal_v2.6.3 && \
    wget https://github.com/hyattpd/Prodigal/releases/download/v2.6.3/prodigal.linux && \
    mv prodigal.linux prodigal && \
    chmod +x prodigal && \
    cd /NGStools

RUN wget https://github.com/samtools/samtools/releases/download/1.3.1/samtools-1.3.1.tar.bz2 && \
    tar xf samtools-1.3.1.tar.bz2 && \
    rm samtools-1.3.1.tar.bz2 && \
    cd samtools-1.3.1 && \
    ./configure && \
    make && \
    rm *.o && \
    cd /NGStools

RUN wget https://github.com/mummer4/mummer/releases/download/v4.0.0beta2/mummer-4.0.0beta2.tar.gz && \
    tar xf mummer-4.0.0beta2.tar.gz && \
    cd mummer-4.0.0beta2 && \
    ./configure && \
    make

ENV PATH="/NGStools/samtools-1.3.1:/NGStools/Prodigal_v2.6.3:/NGStools/bwa-0.7.17:${PATH}"

RUN apt-get remove -y wget bzip2 make g++ && \
    apt-get autoclean -y

WORKDIR /data/
