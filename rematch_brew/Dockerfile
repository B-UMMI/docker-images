FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
# For Linuxbrew
RUN apt-get install -y build-essential curl file git python-setuptools ruby locales
RUN locale-gen en_US.UTF-8 && update-locale
# Change to a non root user
RUN useradd rematch
USER rematch
# Linuxbrew
RUN git clone https://github.com/Linuxbrew/brew.git /NGStools/linuxbrew
ENV PATH="/NGStools/linuxbrew/bin:${PATH}"
ENV MANPATH="/NGStools/linuxbrew/share/man:${MANPATH}"
ENV INFOPATH="/NGStools/linuxbrew/share/info:${INFOPATH}"

# ReMatCh
RUN brew tap tseemann/homebrew-bioinformatics-linux && brew install rematch

CMD rematch --help
