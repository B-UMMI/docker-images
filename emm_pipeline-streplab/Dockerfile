FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="20180629"

WORKDIR /NGStools/

# General dependencies

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget bzip2 git default-jre make g++

# Dependencies
# Miniconda2
RUN wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh && \
    bash Miniconda2-latest-Linux-x86_64.sh -b -p /NGStools/miniconda2 && \
    rm Miniconda2-latest-Linux-x86_64.sh
# PATH
ENV PATH="/NGStools/miniconda2/bin:${PATH}"
# Scipy, pip, cython, Samtools v0.1.18, Bowtie2, Blast
RUN conda update -y -n base conda && \
    conda install -y scipy cython && \
    conda install -y -c bioconda samtools=0.1.18 bowtie2 blast perl-app-cpanminus
# SRST2
RUN git clone https://github.com/katholt/srst2 && \
    pip install srst2/
# A5 pipeline
RUN wget https://sourceforge.net/projects/ngopt/files/a5_miseq_linux_20160825.tar.gz && \
    tar xf a5_miseq_linux_20160825.tar.gz && \
    rm a5_miseq_linux_20160825.tar.gz
# MOSAIK v1
RUN wget https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/mosaik-aligner/Mosaik-1.1.0021-Linux-x64.tar.bz2 && \
    tar xf Mosaik-1.1.0021-Linux-x64.tar.bz2 && \
    rm Mosaik-1.1.0021-Linux-x64.tar.bz2
# Blastall
RUN mkdir /NGStools/blastall && \
    echo '#!/usr/bin/env bash' > /NGStools/blastall/blastall && \
    echo '/NGStools/miniconda2/bin/legacy_blast.pl blastall "$@"' >> /NGStools/blastall/blastall && \
    chmod +x /NGStools/blastall/blastall
# PATH
ENV PATH="/NGStools/blastall:/NGStools/mosaik-aligner/bin:NGStools/a5_miseq_linux_20160825/bin:${PATH}"

# emm_pipeline
RUN git clone https://github.com/streplab/emm_pipeline.git && \
    mv /usr/bin/perl /usr/bin/.perl && \
    ln -s /NGStools/miniconda2/bin/perl /usr/bin/perl && \
    cpanm Exporter::Tiny Test::LeakTrace List::MoreUtils && \
    conda remove -y perl-app-cpanminus
# TODO: problems installing cpanm modules. Change cpanm with ln
# PATH
ENV PATH="/NGStools/emm_pipeline:${PATH}"

# Update emm type database
# Miniconda3, Biopython
RUN wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    bash Miniconda3-latest-Linux-x86_64.sh -b -p /NGStools/miniconda3 && \
    rm Miniconda3-latest-Linux-x86_64.sh && \
    /NGStools/miniconda3/bin/conda update -y -n base conda && \
    /NGStools/miniconda3/bin/conda install -y biopython
# Update DB
RUN wget https://raw.githubusercontent.com/miguelpmachado/randomScripts/master/create_emm_type_db_from_cdc.py && \
    /NGStools/miniconda3/bin/python3 create_emm_type_db_from_cdc.py -o /NGStools/emm_pipeline/

# Clean
RUN apt-get remove -y wget bzip2 git make g++ && \
    apt-get autoclean -y

WORKDIR /data/
