# DOCKERFILE for BBtools
FROM ubuntu:16.04
MAINTAINER Pedro Cerqueira, pedro.cerqueira@medicina.ulisboa.pt

#Update and install dependencies
RUN apt-get update && apt-get -y install \
    bash \
	wget \
    default-jdk

WORKDIR /NGStools/

#Download and untar BBtools
RUN wget https://sourceforge.net/projects/bbmap/files/BBMap_38.44.tar.gz/download -O bbtools.tar.gz && tar -xvzf bbtools.tar.gz

RUN rm bbtools.tar.gz

#Add BBtools to environment variable
ENV PATH="/NGStools/bbmap:$PATH"
