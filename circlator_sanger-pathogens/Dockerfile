FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

# Dependencies

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget bzip2 xz-utils make g++ zlib1g-dev libncurses5-dev libbz2-dev liblzma-dev libcurl4-openssl-dev python python3 python3-pip

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
    rm mummer-4.0.0beta2.tar.gz && \
    cd mummer-4.0.0beta2 && \
    ./configure && \
    make && \
    cd /NGStools

RUN wget http://cab.spbu.ru/files/release3.11.1/SPAdes-3.11.1-Linux.tar.gz && \
    tar xf SPAdes-3.11.1-Linux.tar.gz && \
    rm SPAdes-3.11.1-Linux.tar.gz

RUN wget https://github.com/marbl/canu/releases/download/v1.6/canu-1.6.Linux-amd64.tar.xz && \
    tar xf canu-1.6.Linux-amd64.tar.xz && \
    rm canu-1.6.Linux-amd64.tar.xz

ENV PATH="/NGStools/canu-1.6/Linux-amd64/bin:/NGStools/SPAdes-3.11.1-Linux/bin:/NGStools/mummer-4.0.0beta2:/NGStools/samtools-1.3.1:/NGStools/Prodigal_v2.6.3:/NGStools/bwa-0.7.17:${PATH}"

RUN wget https://github.com/sanger-pathogens/circlator/archive/v1.5.3.tar.gz && \
    tar xf v1.5.3.tar.gz && \
    rm v1.5.3.tar.gz && \
    cd circlator-1.5.3 && \
    python3 setup.py install

RUN apt-get remove -y make g++ python3-pip && \
    apt-get autoclean -y

WORKDIR /data/
