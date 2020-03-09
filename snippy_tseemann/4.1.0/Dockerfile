FROM continuumio/miniconda3:4.7.12-alpine
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="4.1.0-01"

WORKDIR /NGStools/

RUN /opt/conda/bin/conda install -y -c conda-forge -c bioconda -c defaults snippy=4.1.0-0

RUN /opt/conda/bin/conda clean -y --all

ENV PATH /opt/conda/bin:${PATH}

WORKDIR /data/
