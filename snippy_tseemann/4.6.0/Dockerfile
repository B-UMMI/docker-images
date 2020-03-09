FROM continuumio/miniconda3:4.7.12-alpine
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="4.6.0-01"

RUN /opt/conda/bin/conda install -y -c conda-forge -c bioconda -c defaults snippy=4.5.1-0

RUN /opt/conda/bin/conda install -y git

RUN /opt/conda/bin/conda clean -y --all

RUN cd /opt && \
    /opt/conda/bin/git clone https://github.com/tseemann/snippy.git

ENV PATH /opt/snippy/bin:/opt/conda/bin:${PATH}

WORKDIR /data/
