FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="1.2-01"

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y git python3 automake libtool g++ make
# Install parsnp
RUN git clone https://github.com/marbl/parsnp.git && \
    cd parsnp && \
    cd muscle && \
    ./autogen.sh && \
    ./configure && \
    make install && \
    cd .. && \
    ./autogen.sh && \
    ./configure && \
    make install

    wget https://github.com/marbl/parsnp/releases/download/v1.2/parsnp-Linux64-v1.2.tar.gz && \
    tar xf parsnp-Linux64-v1.2.tar.gz && \
    rm parsnp-Linux64-v1.2.tar.gz
ENV PATH="/NGStools/Parsnp-Linux64-v1.2:$PATH"
# Clean
RUN apt-get remove -y wget && \
    apt-get autoclean -y
# Define Workdir
WORKDIR /data/
