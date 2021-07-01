FROM ubuntu:16.04
LABEL author="Miguel Machado <mpmachado@medicina.ulisboa.pt>" version="1.3.0_7ac8d6e-01"

WORKDIR /NGStools/

RUN apt-get update
RUN apt-get install -y git gcc cpp python-pip python-nose python-setuptools python-numpy python-pandas python-pysam python-biopython
RUN pip install typing
RUN pip install --upgrade pysam

RUN git clone https://github.com/snayfach/MIDAS

RUN apt-get install -y wget make bzip2 libncurses5-dev zlib1g-dev libbz2-dev liblzma-dev

RUN wget -nv https://github.com/samtools/samtools/releases/download/1.4/samtools-1.4.tar.bz2 && \
    tar xf samtools-1.4.tar.bz2 && \
    cd samtools-1.4 && \
    ./configure --prefix=/NGStools/samtools-1.4_installation && \
    make && \
    make install && \
    cd ../ && \
    cp samtools-1.4_installation/bin/* MIDAS/bin/Linux/ && \
    rm -r samtools-1.4.tar.bz2 samtools-1.4_installation/

RUN apt-get install -y zip libtbb-dev
RUN wget -nv https://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.3.2/bowtie2-2.3.2-linux-x86_64.zip && \
    unzip bowtie2-2.3.2-linux-x86_64.zip && \
    cp bowtie2-2.3.2/bowtie2* MIDAS/bin/Linux/ && \
    rm -r bowtie2-2.3.2-linux-x86_64.zip bowtie2-2.3.2/

ENV PYTHONPATH="/NGStools/MIDAS:${PYTHONPATH}" PATH="/NGStools/MIDAS/scripts:${PATH}"

# Clean
RUN apt-get remove -y git gcc make bzip2 python-pip wget && apt-get autoclean -y

WORKDIR /data/
