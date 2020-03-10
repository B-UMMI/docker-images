FROM continuumio/miniconda3:4.7.12
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="4.1.0-03"

WORKDIR /NGStools/

RUN conda install -y -c conda-forge -c bioconda -c defaults samtools=1.9 snippy=4.1.0-0

RUN conda clean -y --all

WORKDIR /data/
