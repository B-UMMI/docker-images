FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

RUN apt-get install -y wget
RUN apt-get install -y unzip
RUN apt-get install -y gcc
RUN apt-get install -y g++
RUN apt-get install -y make

# Dependency
RUN apt-get install -y gnutls-bin

RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.6.0/ncbi-blast-2.6.0+-src.zip
RUN unzip ncbi-blast-2.6.0+-src.zip
RUN rm ncbi-blast-2.6.0+-src.zip

WORKDIR /NGStools/ncbi-blast-2.6.0+-src/c++/
RUN ./configure CC='gcc -march=broadwell'
WORKDIR /NGStools/ncbi-blast-2.6.0+-src/c++/ReleaseMT/build/
RUN make all_r

# Clean
RUN apt-get remove -y wget
RUN apt-get remove -y unzip
RUN apt-get remove -y gcc
RUN apt-get remove -y g++
RUN apt-get remove -y make
RUN apt-get autoclean -y

ENV PATH="/NGStools/ncbi-blast-2.6.0+-src/c++/ReleaseMT/bin:${PATH}"
