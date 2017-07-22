FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
RUN apt-get install -y git make sed wget g++ rsync jellyfish
RUN apt-get upgrade -y perl

# Kraken
RUN git clone https://github.com/DerrickWood/kraken.git && mkdir /NGStools/kraken/kraken_instalation/
WORKDIR /NGStools/kraken/
RUN ./install_kraken.sh /NGStools/kraken/kraken_instalation/
ENV PATH="/NGStools/kraken/kraken_instalation:${PATH}"

# minikraken DB
WORKDIR /kraken_db/
RUN wget https://ccb.jhu.edu/software/kraken/dl/minikraken.tgz && tar xf minikraken.tgz && rm minikraken.tgz
ENV KRAKEN_DB_PATH="/kraken_db/:${KRAKEN_DB_PATH}"

# Clean
RUN apt-get remove -y git make && apt-get autoclean -y

WORKDIR /data/
