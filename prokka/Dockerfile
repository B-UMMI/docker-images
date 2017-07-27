FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
RUN apt-get install -y libdatetime-perl libxml-simple-perl libdigest-md5-perl default-jre bioperl curl libpango1.0-dev git wget make python-pip && pip install -U setuptools
# libcairo2-dev

# # HMMER3
# RUN wget http://eddylab.org/software/hmmer3/3.1b2/hmmer-3.1b2-linux-intel-x86_64.tar.gz && tar xf hmmer-3.1b2-linux-intel-x86_64.tar.gz && rm hmmer-3.1b2-linux-intel-x86_64.tar.gz
#
# # # HMMER2
# # RUN wget http://eddylab.org/software/hmmer/2.3.2/hmmer-2.3.2.tar.gz && tar xf hmmer-2.3.2.tar.gz && rm hmmer-2.3.2.tar.gz
#
# Barrnap
RUN wget https://github.com/tseemann/barrnap/archive/0.8.tar.gz && tar xf 0.8.tar.gz && rm 0.8.tar.gz

# Infernal
RUN wget http://eddylab.org/infernal/infernal-1.1.2-linux-intel-gcc.tar.gz && tar xf infernal-1.1.2-linux-intel-gcc.tar.gz && rm infernal-1.1.2-linux-intel-gcc.tar.gz && cd infernal-1.1.2-linux-intel-gcc && ./configure && make && make install && cd easel && make install && cd /NGStools && rm -rf infernal-1.1.2-linux-intel-gcc/

# Sequin
RUN mkdir sequin_20170222 && cd sequin_20170222 && wget ftp://ftp.ncbi.nih.gov/sequin/CURRENT/sequin.linux-x86_64.tar.gz && tar xf sequin.linux-x86_64.tar.gz && rm sequin.linux-x86_64.tar.gz && cd /NGStools

# GenomeTools
RUN wget http://genometools.org/pub/genometools-1.5.9.tar.gz && tar xf genometools-1.5.9.tar.gz && rm genometools-1.5.9.tar.gz && cd genometools-1.5.9 && make && make install && cd gtpython && python setup.py install && cd /NGStools && rm -rf genometools-1.5.9/

# gff3toembl
RUN mkdir gff3toembl && cd gff3toembl && git clone https://github.com/sanger-pathogens/gff3toembl.git && python gff3toembl/setup.py install && cd /NGStools

# Blast+
RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.6.0/ncbi-blast-2.6.0+-x64-linux.tar.gz && tar xf ncbi-blast-2.6.0+-x64-linux.tar.gz && rm ncbi-blast-2.6.0+-x64-linux.tar.gz

# CD-HIT
RUN wget https://github.com/weizhongli/cdhit/releases/download/V4.6.8/cd-hit-v4.6.8-2017-0621-source.tar.gz && tar xf cd-hit-v4.6.8-2017-0621-source.tar.gz && rm cd-hit-v4.6.8-2017-0621-source.tar.gz && cd cd-hit-v4.6.8-2017-0621 && make && cd cd-hit-auxtools && make && cd /NGStools

# Exonerate
RUN wget http://ftp.ebi.ac.uk/pub/software/vertebrategenomics/exonerate/exonerate-2.2.0-x86_64.tar.gz && tar xf exonerate-2.2.0-x86_64.tar.gz --no-same-owner && chmod 755 exonerate-2.2.0-x86_64/ && rm exonerate-2.2.0-x86_64.tar.gz

# Prokka
RUN git clone https://github.com/tseemann/prokka.git && prokka/bin/prokka --setupdb

ENV PATH="/NGStools/barrnap-0.8/bin:/NGStools/sequin_20170222:/NGStools/gff3toembl/gff3toembl/scripts:/NGStools/ncbi-blast-2.6.0+/bin:/NGStools/cd-hit-v4.6.8-2017-0621:/NGStools/cd-hit-v4.6.8-2017-0621/cd-hit-auxtools:/NGStools/exonerate-2.2.0-x86_64/bin:/NGStools/prokka/bin:${PATH}"
#/NGStools/hmmer-3.1b2-linux-intel-x86_64/binaries:

# Clean
RUN pip uninstall -y setuptools && apt-get remove -y git wget make python-pip && apt-get autoclean -y

WORKDIR /data/
