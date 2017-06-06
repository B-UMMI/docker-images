FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

# Create a non root user
RUN useradd --create-home --home-dir /NGStools/ ubuntu

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
# For Bio Perl
RUN apt-get install -y make cpanminus
# Bio Perl
RUN cpanm Bio::Perl
# For Linuxbrew
# RUN apt-get install -y build-essential curl file git python-setuptools ruby locales
RUN apt-get install -y build-essential curl file git python-setuptools ruby
# RUN locale-gen en_US.UTF-8 && update-locale
# Change to the non root user
USER ubuntu
# Linuxbrew
RUN ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install)"
# RUN git clone https://github.com/Linuxbrew/brew.git /NGStools/linuxbrew
# ENV PATH="/NGStools/linuxbrew/bin:${PATH}"
# ENV MANPATH="/NGStools/linuxbrew/share/man:${MANPATH}"
# ENV INFOPATH="/NGStools/linuxbrew/share/info:${INFOPATH}"
#
# # Snippy
# RUN brew tap homebrew/science && brew tap tseemann/homebrew-bioinformatics-linux && brew install snippy
#
# CMD snippy --help
