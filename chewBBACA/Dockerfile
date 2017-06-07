#USE BLAST BINARIES FROM UMMIDOCK REPO
FROM ummidock/blast_binaries:2.6.0-binaries
MAINTAINER Bruno Gonçalves, bfgoncalves@medicina.ulisboa.pt

WORKDIR /NGStools/

RUN apt-get update
RUN apt-get install -y git make python-dev gcc wget libxml2-dev libxslt1-dev zlib1g-dev g++ build-essential python-numpy

#INSTALL PIP
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

#GET chewBBACA and Prodigal
RUN git clone https://github.com/hyattpd/Prodigal.git
RUN git clone https://github.com/mickaelsilva/chewBBACA.git

#INSTALL chewBBACA requirements
WORKDIR /NGStools/chewBBACA
RUN pip2 install -r requirements.txt
RUN pip2 install --upgrade numpy

#INSTALL PRODIGAL
WORKDIR /NGStools/Prodigal
RUN make install

WORKDIR /NGStools/

#ADD chewBBACA TO PATH
ENV PATH="/NGStools/chewBBACA:${PATH}"
ENV PATH="/NGStools/chewBBACA/utils:${PATH}"
ENV PATH="/NGStools/chewBBACA/allelecall:${PATH}"
ENV PATH="/NGStools/chewBBACA/createschema:${PATH}"
ENV PATH="/NGStools/chewBBACA/SchemaEvaluator:${PATH}"