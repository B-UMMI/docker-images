# DOCKERFILE for abricate https://github.com/tseemann/abricate
FROM ubuntu:16.04
MAINTAINER M Ramirez, ramirez@fm.ul.pt

RUN apt-get update && apt-get -y install \
	bzip2 \
	gzip \
	wget \
	git
# git needs to be present to allow DB update

WORKDIR /NGStools

RUN sudo apt-get install emboss bioperl ncbi-blast+ gzip unzip \
  libjson-perl libtext-csv-perl libfile-slurp-perl liblwp-protocol-https-perl libwww-perl
RUN git clone https://github.com/tseemann/abricate.git
RUN ./abricate/bin/abricate --check
RUN ./abricate/bin/abricate --setupdb
ENV PATH="/NGStools/abricate/bin:$PATH"

WORKDIR /data/
