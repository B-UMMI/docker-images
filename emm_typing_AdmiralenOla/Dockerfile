FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="0.3"

WORKDIR /NGStools/

# General dependencies
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y git python3 python3-pip && \
    pip3 install setuptools

# Install emm_typing
RUN git clone https://github.com/AdmiralenOla/emm_typing.git && \
    cd emm_typing && \
    python3 setup.py install

# Clean
RUN apt-get remove -y git python3-pip && \
    apt-get autoclean -y

WORKDIR /data/
