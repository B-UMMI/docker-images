FROM ubuntu:22.04
MAINTAINER UMMI, imm-bioinfo@medicina.ulisboa.pt

WORKDIR /NGStools

# -- General Dependencies ---
RUN apt-get update
RUN apt-get install -y wget g++ bioperl gzip unzip git libjson-perl libtext-csv-perl libpath-tiny-perl liblwp-protocol-https-perl libwww-perl

# BLAST
RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.9.0/ncbi-blast-2.9.0+-x64-linux.tar.gz && \
    tar -xf ncbi-blast-2.9.0+-x64-linux.tar.gz && \
    rm ncbi-blast-2.9.0+-x64-linux.tar.gz

# any2fasta
RUN git clone https://github.com/tseemann/any2fasta.git

# INSTALL Abricate
RUN git clone https://github.com/tseemann/abricate.git
# Add BLAST, any2fasta and Abricate to PATH
ENV PATH="/NGStools/ncbi-blast-2.9.0+/bin:/NGStools/any2fasta:/NGStools/abricate/bin:${PATH}"
RUN abricate --check && abricate --setupdb

# Update DBs
RUN abricate-get_db --db argannot --force
RUN abricate-get_db --db card --force
RUN abricate-get_db --db ecoh --force
RUN abricate-get_db --db ecoli_vf --force
# Cannot update megares
#RUN abricate-get_db --db megares --force
RUN abricate-get_db --db ncbi --force
RUN abricate-get_db --db plasmidfinder --force
RUN abricate-get_db --db resfinder --force
RUN abricate-get_db --db vfdb --force

WORKDIR /NGStools
