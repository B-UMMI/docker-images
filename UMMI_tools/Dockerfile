FROM ummidock/chewBBACA:latest

RUN apt-get update
RUN apt-get install default-jdk git make python-dev gcc wget g++

# Create a non root user
RUN useradd --create-home --home-dir /NGStools/ ubuntu

WORKDIR /NGStools/

# INSTALL Linuxbrew
RUN git clone https://github.com/Linuxbrew/brew.git /NGStools/linuxbrew
ENV PATH="/NGStools/linuxbrew/bin:${PATH}"
ENV MANPATH="/NGStools/linuxbrew/share/man:${MANPATH}"
ENV INFOPATH="/NGStools/linuxbrew/share/info:${INFOPATH}"

# Change to the non root user
USER ubuntu

#INSTALL Torsteen's MLST
RUN brew tap homebrew/science
RUN brew update
RUN brew install mlst

#CHANGE TO ROOT
USER root

#INSTALL INNUca
RUN git clone https://github.com/B-UMMI/INNUca.git

#INSTALL ReMatCh
RUN git clone https://github.com/B-UMMI/ReMatCh.git

#INSTALL PathoTyping
RUN git clone https://github.com/B-UMMI/patho_typing.git

#ADD Programs to PATH
ENV PATH="/NGStools/INNUca:${PATH}"
ENV ENV PATH="/NGStools/ReMatCh:${PATH}"
ENV ENV PATH="/NGStools/patho_typing:${PATH}"