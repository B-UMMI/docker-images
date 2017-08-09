FROM ubuntu:latest
MAINTAINER UMMI
LABEL email="ummimicro@medicina.ulisboa.pt"

RUN apt-get update && apt-get install -y \
    ftp && \
    apt-get autoclean -y

RUN apt-get update && apt-get install -y \
    p7zip-full && \
    apt-get autoclean -y
    
WORKDIR /data/
