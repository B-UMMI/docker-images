FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
RUN apt-get install -y git make sed wget g++ rsync locales && locale-gen en_GB.UTF-8 && update-locale
ENV LANG="en_GB.UTF-8"
RUN apt-get upgrade -y perl

# Jellyfish v1.1.10-1
RUN wget https://launchpad.net/ubuntu/+archive/primary/+files/jellyfish_1.1.10.orig.tar.gz && tar xf jellyfish_1.1.10.orig.tar.gz && rm jellyfish_1.1.10.orig.tar.gz && cd /NGStools/jellyfish-1.1.10/ && ./configure && make && make install && rm -r /NGStools/jellyfish-1.1.10/
ENV LD_LIBRARY_PATH="/usr/local/lib:${LD_LIBRARY_PATH}"

# Kraken
RUN cd /NGStools/ && git clone https://github.com/DerrickWood/kraken.git && mkdir /NGStools/kraken/kraken_instalation/ && cd /NGStools/kraken/ && ./install_kraken.sh /NGStools/kraken/kraken_instalation/
ENV PATH="/NGStools/kraken/kraken_instalation:${PATH}"

# minikraken DB
RUN mkdir /kraken_db/ && cd /kraken_db/ && wget https://ccb.jhu.edu/software/kraken/dl/minikraken.tgz && tar xf minikraken.tgz && rm minikraken.tgz
ENV KRAKEN_DB_PATH="/kraken_db:${KRAKEN_DB_PATH}"

# Clean
RUN apt-get remove -y git make locales && apt-get autoclean -y

WORKDIR /data/
