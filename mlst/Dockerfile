FROM perl:5.38.0
MAINTAINER UMMI, imm-bioinfo@medicina.ulisboa.pt

WORKDIR /NGStools/

RUN apt-get update

# -- General Dependencies ---
RUN apt-get install -y git wget g++

# -- mlst Dependencies --
# Blast
RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.9.0/ncbi-blast-2.9.0+-x64-linux.tar.gz && \
    tar -xf ncbi-blast-2.9.0+-x64-linux.tar.gz && \
    rm ncbi-blast-2.9.0+-x64-linux.tar.gz
# any2fasta
RUN git clone https://github.com/tseemann/any2fasta.git
# Perl libs
RUN cpan Moo List::MoreUtils JSON

ENV PATH="/NGStools/ncbi-blast-2.9.0+/bin:/NGStools/any2fasta:${PATH}"

# --- mlst ----
RUN git clone https://github.com/tseemann/mlst.git
ENV PATH="/NGStools/mlst/bin:${PATH}"

# Script to update the mlst database
# Remove old script to ownload FASTA files
RUN rm /NGStools/mlst/scripts/mlst-download_pub_mlst
# Download new script
RUN wget https://raw.githubusercontent.com/B-UMMI/docker-images/master/mlst/mlst-download_pub_mlst
RUN chmod 755 mlst-download_pub_mlst
RUN ./mlst-download_pub_mlst
RUN rm -r /NGStools/mlst/db/pubmlst/
RUN mv /NGStools/pubmlst /NGStools/mlst/db/
RUN cd /NGStools/mlst/scripts && ls && ./mlst-make_blast_db

# Update Clostridium to Clostridioides
RUN echo 'cdifficile\tClostridioides\tdifficile' >> /NGStools/mlst/db/scheme_species_map.tab
