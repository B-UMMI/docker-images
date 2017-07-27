FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
RUN apt-get install -y libdatetime-perl libxml-simple-perl libdigest-md5-perl default-jre bioperl curl git wget make python-pip && pip install -U setuptools

# # HMMER3
# RUN wget http://eddylab.org/software/hmmer3/3.1b2/hmmer-3.1b2-linux-intel-x86_64.tar.gz && tar xf hmmer-3.1b2-linux-intel-x86_64.tar.gz && rm hmmer-3.1b2-linux-intel-x86_64.tar.gz
#
# # # HMMER2
# # RUN wget http://eddylab.org/software/hmmer/2.3.2/hmmer-2.3.2.tar.gz && tar xf hmmer-2.3.2.tar.gz && rm hmmer-2.3.2.tar.gz
#
# Barrnap
RUN wget https://github.com/tseemann/barrnap/archive/0.8.tar.gz && tar xf 0.8.tar.gz && rm 0.8.tar.gz

# Infernal
RUN wget http://eddylab.org/infernal/infernal-1.1.2-linux-intel-gcc.tar.gz && tar xf infernal-1.1.2-linux-intel-gcc.tar.gz && rm infernal-1.1.2-linux-intel-gcc.tar.gz && cd infernal-1.1.2-linux-intel-gcc && ./configure && make && make install && cd /NGStools

# Sequin
RUN mkdir sequin_20170222 && cd sequin_20170222 && wget ftp://ftp.ncbi.nih.gov/sequin/CURRENT/sequin.linux-x86_64.tar.gz && tar xf sequin.linux-x86_64.tar.gz && rm sequin.linux-x86_64.tar.gz && cd /NGStools

# GenomeTools
RUN wget http://genometools.org/pub/binary_distributions/gt-1.5.9-Linux_x86_64-64bit-complete.tar.gz && tar xf gt-1.5.9-Linux_x86_64-64bit-complete.tar.gz && rm gt-1.5.9-Linux_x86_64-64bit-complete.tar.gz && python /NGStools/gt-1.5.9-Linux_x86_64-64bit-complete/gtpython/setup.py install

# gff3toembl
RUN git clone https://github.com/sanger-pathogens/gff3toembl.git && python gff3toembl/setup.py install

# CD-HIT
RUN wget https://github.com/weizhongli/cdhit/releases/download/V4.6.8/cd-hit-v4.6.8-2017-0621-source.tar.gz && tar xf cd-hit-v4.6.8-2017-0621-source.tar.gz && rm cd-hit-v4.6.8-2017-0621-source.tar.gz && cd cd-hit-v4.6.8-2017-0621 && make && cd cd-hit-auxtools && make && cd /NGStools

# Exonerate
RUN wget http://ftp.ebi.ac.uk/pub/software/vertebrategenomics/exonerate/exonerate-2.2.0-x86_64.tar.gz && tar xf --no-same-owner exonerate-2.2.0-x86_64.tar.gz && rm exonerate-2.2.0-x86_64.tar.gz

# Prokka
RUN git clone https://github.com/tseemann/prokka.git && prokka/bin/prokka --setupdb

ENV PATH="/NGStools/barrnap-0.8/bin:/NGStools/gt-1.5.9-Linux_x86_64-64bit-complete/bin:/NGStools/gff3toembl/scripts:/NGStools/prokka/bin:${PATH}"
#/NGStools/hmmer-3.1b2-linux-intel-x86_64/binaries:

# Clean
RUN pip uninstall -y setuptools && apt-get remove -y git wget make python-pip && apt-get autoclean -y

WORKDIR /data/
