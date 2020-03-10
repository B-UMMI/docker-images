FROM continuumio/miniconda3:4.7.12
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="4.6.0-02"

WORKDIR /NGStools/

RUN conda install -y -c conda-forge -c bioconda -c defaults snippy=4.5.1-0

RUN conda clean -y --all

RUN git clone https://github.com/tseemann/snippy.git

RUN echo 'export PATH="/NGStools/snippy/bin:${PATH}"' >> ~/.bashrc

WORKDIR /data/
