FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

RUN apt-get install -y wget
RUN apt-get install -y tar

# Dependencies
# Blast+
RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.6.0/ncbi-blast-2.6.0+-x64-linux.tar.gz && tar xf ncbi-blast-2.6.0+-x64-linux.tar.gz && rm ncbi-blast-2.6.0+-x64-linux.tar.gz

ENV PATH="/NGStools/ncbi-blast-2.6.0+/bin:${PATH}"

# Dependencies
# Perl lib
RUN apt-get upgrade perl && apt-get install -y libmoo-perl liblist-moreutils-perl

# MLST
RUN wget https://github.com/tseemann/mlst/archive/2.9.tar.gz && tar xf 2.9.tar.gz
