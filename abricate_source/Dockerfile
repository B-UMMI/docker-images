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

# Install dependencies
RUN apt-get install -y  emboss bioperl ncbi-blast+ gzip unzip \
  libjson-perl libtext-csv-perl libfile-slurp-perl liblwp-protocol-https-perl libwww-perl

# ADD Virulence_finder database
RUN git clone https://bitbucket.org/genomicepidemiology/virulencefinder_db.git && cd virulencefinder_db && cat *.fsa >> sequences
# ADD BacMet database
RUN mkdir /NGStools/bacmet
WORKDIR /NGStools/bacmet
RUN wget http://bacmet.biomedicine.gu.se/download/BacMet2_EXP_database.fasta
RUN mv BacMet2_EXP_database.fasta sequences

WORKDIR /NGStools

# Install abricate - through git clone
RUN git clone https://github.com/tseemann/abricate.git

RUN mkdir /NGStools/abricate/db/virulencefinder && cp /NGStools/virulencefinder_db/sequences /NGStools/abricate/db/virulencefinder/
RUN mkdir /NGStools/abricate/db/bacmet && cp /NGStools/bacmet/sequences /NGStools/abricate/db/bacmet/

RUN ./abricate/bin/abricate --check
RUN ./abricate/bin/abricate --setupdb
ENV PATH="/NGStools/abricate/bin:$PATH"

WORKDIR /data/
