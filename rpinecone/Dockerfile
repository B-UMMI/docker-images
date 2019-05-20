FROM r-base:3.6.0
MAINTAINER Miguel Machado <miguel.machado@insa.min-saude.pt>
LABEL version="20190520-01"

RUN apt-get update

RUN apt-get install -y libcurl4-openssl-dev libssl-dev libmagick++-dev

RUN Rscript -e 'install.packages("devtools", clean = TRUE)'
RUN Rscript -e 'devtools::install_github("alexwailan/rpinecone")'

RUN apt-get autoclean -y

WORKDIR /data/
