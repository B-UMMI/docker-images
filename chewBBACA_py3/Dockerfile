#USE BLAST BINARIES FROM UMMIDOCK REPO
FROM ummidock/blast_binaries:2.9.0-binaries
MAINTAINER Inês Mendes, cimendes@medicina.ulisboa.pt

WORKDIR /NGStools/

RUN apt-get update && apt-get install -y \
	git \
	make \
	gcc \
	wget \
	libxml2-dev \
	libxslt1-dev \
	libblas-dev \
	liblapack-dev \
	zlib1g-dev \
	g++ \
	build-essential

# INSTALL CONDA
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN chmod +x Miniconda3-latest-Linux-x86_64.sh
RUN ./Miniconda3-latest-Linux-x86_64.sh -b -p /NGStools/miniconda
ENV PATH="/NGStools/miniconda/bin:$PATH"
RUN python -m pip install --upgrade pip

#GET chewBBACA and Prodigal
RUN git clone https://github.com/hyattpd/Prodigal.git
RUN git clone https://github.com/B-UMMI/chewBBACA.git

#INSTALL chewBBACA requirements
WORKDIR /NGStools/chewBBACA
ENV LANG C.UTF-8
RUN python3 setup.py install

#INSTALL PRODIGAL
WORKDIR /NGStools/Prodigal
RUN make install

WORKDIR /NGStools/

#install mafft and clustalw2 to run schema evaluator
RUN wget www.clustal.org/download/current/clustalw-2.1-linux-x86_64-libcppstatic.tar.gz
RUN tar -zxf clustalw-2.1-linux-x86_64-libcppstatic.tar.gz
RUN rm clustalw-2.1-linux-x86_64-libcppstatic.tar.gz
ENV PATH="/NGStools/clustalw-2.1-linux-x86_64-libcppstatic:${PATH}"

RUN apt-get autoclean
RUN apt-get autoremove
RUN apt-get clean
RUN apt-get install -y mafft

#ADD chewBBACA TO PATH
ENV PATH="/NGStools/chewBBACA:${PATH}"
ENV PATH="/NGStools/chewBBACA/utils:${PATH}"
ENV PATH="/NGStools/chewBBACA/allelecall:${PATH}"
ENV PATH="/NGStools/chewBBACA/createschema:${PATH}"
ENV PATH="/NGStools/chewBBACA/SchemaEvaluator:${PATH}"
