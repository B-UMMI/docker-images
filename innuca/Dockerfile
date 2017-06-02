FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

RUN apt-get install -y wget
RUN apt-get install -y tar

RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.6.0/ncbi-blast-2.6.0+-x64-linux.tar.gz
RUN tar xf ncbi-blast-2.6.0+-x64-linux.tar.gz
