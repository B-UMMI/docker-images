FROM ubuntu:latest
MAINTAINER UMMI
LABEL email="ummimicro@medicina.ulisboa.pt"

RUN apt-get update && apt-get install -y \
    ftp && \
    apt-get autoclean -y

WORKDIR /data/
