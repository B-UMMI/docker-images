#DOCKERFILE FOR BIONODE-WATERMILL
FROM docker-images/bionode-ncbi
MAINTAINER Tiago Jesus, tiagojesus@medicina.ulisboa.pt

#SET WORKDIR
#WORKDIR /bionode/ #inherited from docker-images/bionode-ncbi
#INSTALL DEPENDENCIES
RUN apt-get update
RUN apt-get install -y git

#CLONE BIONODE-WATERMILL FROM GIT HUB
RUN git clone https://github.com/bionode/bionode-watermill.git

#INSTALL WATERMILL WITHIN GIT DIRECTORY
RUN npm install
RUN npm link

#NEEDS TESTING
RUN bionode-watermill
