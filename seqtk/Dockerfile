# DOCKERFILE for seqtk
FROM ubuntu:16.04
MAINTAINER Pedro Cerqueira, pedro.cerqueira@medicina.ulisboa.pt


WORKDIR /NGStools/

#Update and install dependencies
RUN apt-get update && apt-get -y install \
	bash \
    build-essential \
    make \
    git \
    zlib1g-dev

#Clone seqtk from GitHub repo
RUN git clone https://github.com/lh3/seqtk.git

WORKDIR /NGStools/seqtk

#Build seqtk
RUN make

#Add seqtk to 
ENV PATH="/NGStools/seqtk:$PATH"

