FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

# Dependencies
RUN apt-get update && apt-get install -y python-dev build-essential git wget locales && locale-gen --purge en_US.UTF-8 && DEBIAN_FRONTEND="noninteractive" dpkg-reconfigure locales && update-locale LANG=en_US.UTF-8 LANGUAGE=en_US.UTF-8 LC_ALL=en_US.UTF-8

# # yaggo
# RUN git clone https://github.com/gmarcais/yaggo.git && cd yaggo && make && cd..

# MUMmer
RUN wget https://github.com/mummer4/mummer/releases/download/v4.0.0beta1/mummer-4.0.0beta1.tar.gz && tar xf mummer-4.0.0beta1.tar.gz && rm mummer-4.0.0beta1.tar.gz && cd mummer-4.0.0beta1 && ./configure --enable-python-binding && make && make install && cd .. && rm -rf mummer-4.0.0beta1/

# blastall
RUN wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/legacy/2.2.26/blast-2.2.26-x64-linux.tar.gz && tar xf blast-2.2.26-x64-linux.tar.gz && rm blast-2.2.26-x64-linux.tar.gz

# ABACAS
RUN mkdir abacas && cd abacas && wget https://downloads.sourceforge.net/project/abacas/abacas.1.3.1.pl && sed -i "s&#!/usr/local/bin/perl -w&#!/usr/bin/env perl&1" abacas.1.3.1.pl && chmod 755 abacas.1.3.1.pl && ln -s /NGStools/abacas/abacas.1.3.1.pl /NGStools/abacas/abacas.pl && cd ..

ENV PATH="/NGStools/blast-2.2.26/bin:/NGStools/abacas:${PATH}"

# Clean
RUN apt-get remove -y build-essential git wget locales && apt-get autoclean -y

WORKDIR /data/
