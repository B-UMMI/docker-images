 
FROM perl:5.30-slim-stretch
MAINTAINER Inês Mendes <cimendes@medicina.ulisboa.pt>
LABEL version="2.19.0"

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

# fixing permissions for MLST update
#RUN chmod +x /NGStools/INNUca/Docker/update_mlst_db.sh && chmod o+wr /NGStools/mlst/scripts/ && chmod -R o+wr /NGStools/mlst/db/ && sed -i "s#OUTDIR=pubmlst#OUTDIR=/NGStools/mlst/scripts/pubmlst#1" /NGStools/mlst/scripts/mlst-download_pub_mlst

#script to update the mlst database
RUN /NGStools/mlst/scripts/mlst-download_pub_mlst | bash
RUN rm -r /NGStools/mlst/db/pubmlst/
RUN mv pubmlst /NGStools/mlst/db/
RUN cd /NGStools/mlst/scripts && ls  && ./mlst-make_blast_db

# Update Clostridium to Clostridioides
RUN echo 'cdifficile\tClostridioides\tdifficile' >> /NGStools/mlst/db/scheme_species_map.tab

