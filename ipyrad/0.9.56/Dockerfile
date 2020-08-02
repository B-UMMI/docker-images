FROM continuumio/miniconda3:4.8.2-alpine
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="0.9.56-02"

RUN /opt/conda/bin/conda install -y -c conda-forge -c bioconda ipyrad=0.9.56 notebook mpi4py bash

RUN /opt/conda/bin/conda clean -y --all

ENV PATH="/opt/conda/bin:${PATH}"

WORKDIR /data/

# Default command
CMD ipyrad --help
