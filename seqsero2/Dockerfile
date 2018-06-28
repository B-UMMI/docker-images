FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="alpha-test"

WORKDIR /NGStools/

# General dependencies

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget bzip2 git

# Dependencies
# Miniconda3
RUN wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    bash Miniconda3-latest-Linux-x86_64.sh -b -p /NGStools/miniconda3 && \
    rm Miniconda3-latest-Linux-x86_64.sh
# SRA toolkit
RUN wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/current/sratoolkit.current-ubuntu64.tar.gz && \
    tar xf sratoolkit.current-ubuntu64.tar.gz && \
    rm sratoolkit.current-ubuntu64.tar.gz
# SalmID
RUN git clone --recursive https://github.com/hcdenbakker/SalmID.git && \
    chmod +x SalmID/SalmID.py
# PATH
ENV PATH="/NGStools/miniconda3/bin:/NGStools/sratoolkit.2.9.1-ubuntu64/bin:/NGStools/SalmID:${PATH}"
# Biopython, BWA, Samtools, Blast, SPAdes, Bedtools
RUN conda update -y -n base conda && \
    conda install -y biopython && \
    conda install -y -c bioconda bwa samtools blast spades bedtools

# SeqSero2
RUN git clone https://github.com/denglab/SeqSero2.git
# PATH
ENV PATH="/NGStools/miniconda3/bin:/NGStools/sratoolkit.2.9.1-ubuntu64/bin:/NGStools/SalmID:/NGStools/SeqSero2:${PATH}"

# Clean

RUN apt-get remove -y wget bzip2 git && \
    apt-get autoclean -y

WORKDIR /data/
