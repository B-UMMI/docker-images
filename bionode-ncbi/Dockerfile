#DOCKERFILE FOR BIONODE-NCBI
FROM ubuntu:16.04
MAINTAINER Bruno Gonçalves, bfgoncalves@medicina.ulisboa.pt

#SET WORKDIR
WORKDIR /NGStools/
#INSTALL DEPENDENCIES
RUN apt-get update
RUN apt-get install -y npm sudo curl

# INSTALL node.js version 7
RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
RUN apt-get install -y nodejs

RUN npm install bionode-ncbi -g

# This can be tested with docker run -it <img> sh
# > bionode-ncbi -h
