FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="1.2-01"

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y wget python3
# Install parsnp
RUN wget https://github.com/marbl/parsnp/releases/download/v1.2/parsnp-Linux64-v1.2.tar.gz && \
    tar xf parsnp-Linux64-v1.2.tar.gz && \
    rm parsnp-Linux64-v1.2.tar.gz
# Clean
RUN apt-get remove -y wget && \
    apt-get autoclean -y
# Define Workdir
WORKDIR /data/
