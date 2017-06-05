FROM ubuntu:16.04
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>

WORKDIR /NGStools/

RUN apt-get update

# Dependencies
# Linuxbrew
RUN apt-get install -y build-essential curl file git python-setuptools ruby

RUN brew tap tseemann/homebrew-bioinformatics-linux && brew install rematch

CMD rematch --help
