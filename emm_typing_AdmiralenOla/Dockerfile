FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="0.4-01"

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y git python3 python3-pip ncbi-blast+ && \
    pip3 install setuptools
# Install emm_typing
RUN git clone https://github.com/miguelpmachado/emm_typing.git && \
    cd emm_typing && \
    python3 setup.py install && \
    cd /NGStools
# Change PYTHON_EGG_CACHE
ENV PYTHON_EGG_CACHE=/tmp
# Clean
RUN apt-get remove -y git python3-pip && \
    apt-get autoclean -y
# Define Workdir
WORKDIR /data/
