#DOCKERFILE FOR BIONODE-WATERMILL
#FROM docker-images/bionode-ncbi
FROM ubuntu:16.04
MAINTAINER Tiago Jesus, tiagojesus@medicina.ulisboa.pt

#SET WORKDIR
WORKDIR /NGStools/
#INSTALL DEPENDENCIES
RUN apt-get update
RUN apt-get install -y git

#CLONE BIONODE-WATERMILL FROM GIT HUB
RUN git clone https://github.com/bionode/bionode-watermill.git

#CHANGE DIRECTORY TO BIONODE-WATERMILL

WORKDIR ./bionode-watermill

#INSTALL WATERMILL WITHIN GIT DIRECTORY
RUN npm install
RUN npm link

#NEEDS TESTING
RUN bionode-watermill
