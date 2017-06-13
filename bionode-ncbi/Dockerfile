#DOCKERFILE FOR BIONODE-NCBI
FROM ubuntu:16.04
MAINTAINER Bruno Gonçalves, bfgoncalves@medicina.ulisboa.pt

#SET WORKDIR
WORKDIR /NGStools/
#INSTALL DEPENDENCIES
RUN apt-get update
RUN apt-get install -y nodejs npm

#UBUNTU IS SOMEHOW STUPID... and decides to break all npm modules xD
RUN ln -s `which nodejs` /usr/bin/node

RUN npm install bionode-ncbi -g

# This can be tested with docker run -it <img> sh
# > bionode-ncbi -h
