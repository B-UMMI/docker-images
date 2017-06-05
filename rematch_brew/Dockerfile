FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
# Linuxbrew
RUN apt-get install -y build-essential curl file git python-setuptools ruby
RUN git clone https://github.com/Linuxbrew/brew.git ~/.linuxbrew
ENV PATH="$HOME/.linuxbrew/bin:${PATH}"
ENV MANPATH="$(brew --prefix)/share/man:${MANPATH}"
ENV INFOPATH="$(brew --prefix)/share/info:${INFOPATH}"

# ReMatCh
RUN brew tap tseemann/homebrew-bioinformatics-linux && brew install rematch

CMD rematch --help
