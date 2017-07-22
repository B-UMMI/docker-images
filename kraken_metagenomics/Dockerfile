FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

RUN apt-get install git sed find wget g++ rsync jellyfish
RUN apt-get upgrade -y perl

RUN git clone https://github.com/DerrickWood/kraken.git

WORKDIR /kraken_db/
RUN wget https://ccb.jhu.edu/software/kraken/dl/minikraken.tgz && tar xf minikraken.tgz
