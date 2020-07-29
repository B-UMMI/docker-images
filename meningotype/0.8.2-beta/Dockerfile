FROM continuumio/miniconda2:4.7.12
MAINTAINER Miguel Machado <mpmachado@medicina.ulisboa.pt>
LABEL version="0.8.2-beta-01"

# Install dependencies
RUN conda install -y -c conda-forge -c bioconda -c defaults blast=2.7.1 mlst ispcr biopython=1.73

# Install meningotype
RUN pip install git+https://github.com/MDU-PHL/meningotype.git

WORKDIR /data/

## Default command
CMD meningotype --test
