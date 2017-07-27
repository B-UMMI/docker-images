FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
RUN apt-get install -y libdatetime-perl libxml-simple-perl libdigest-md5-perl default-jre bioperl git wget

# # HMMER3
# RUN wget http://eddylab.org/software/hmmer3/3.1b2/hmmer-3.1b2-linux-intel-x86_64.tar.gz && tar xf hmmer-3.1b2-linux-intel-x86_64.tar.gz && rm hmmer-3.1b2-linux-intel-x86_64.tar.gz
#
# # # HMMER2
# # RUN wget http://eddylab.org/software/hmmer/2.3.2/hmmer-2.3.2.tar.gz && tar xf hmmer-2.3.2.tar.gz && rm hmmer-2.3.2.tar.gz
#
# # Barrnap
# RUN wget https://github.com/tseemann/barrnap/archive/0.8.tar.gz && tar xf 0.8.tar.gz && rm 0.8.tar.gz
#
# # ARAGORN
# RUN wget http://mbio-serv2.mbioekol.lu.se/ARAGORN/Downloads/aragorn1.2.38.tgz && tar xf aragorn1.2.38.tgz && rm aragorn1.2.38.tgz

# Prokka
RUN git clone https://github.com/tseemann/prokka.git && prokka/bin/prokka --setupdb

ENV PATH="/NGStools/hmmer-3.1b2-linux-intel-x86_64/binaries:/NGStools/barrnap-0.8/bin:/NGStools/prokka/bin:${PATH}"

# Clean
RUN apt-get remove -y git wget && apt-get autoclean -y

WORKDIR /data/
