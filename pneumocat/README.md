PneumoCaT - Docker
==================
Pneumococcal Capsular Typing tool for NGS data

<https://github.com/phe-bioinformatics/PneumoCaT>


This is a dockerfile for using INNUca, with all dependencies already installed.

Within this container you can find:
- ubuntu:16.04
- git
- make
- unzip
- Python v2.7 and pip
- PyYaml numpy lxml pysam and biopython
- [Bowtie2](https://sourceforge.net/projects/bowtie-bio/files/bowtie2/2.2.9/)
- [samtools-0.1.19](https://sourceforge.net/projects/samtools/files/samtools/0.1.19/)
- [PneumoCaT](https://github.com/phe-bioinformatics/PneumoCaT)

### Using play-with-docker
[![Try in PWD](https://cdn.rawgit.com/play-with-docker/stacks/cff22438/assets/images/button.png)](http://labs.play-with-docker.com/)

Within [play-with-docker](http://labs.play-with-docker.com/) webpage click on **create session**. Then, another page
will open with a big counter on the upper left corner. Click on **+ add new instance** and a terminal like instance should be generated on the right. On
this terminal you can load this docker image as follows:

`docker pull ummidock/pneumocat`

#### Build this docker on your local machine

For this, docker needs to be installed on your machine. Instructions for this can be found [here](https://docs.docker.com/engine/installation/).

##### Using DockerHub (automated build image)

`docker pull ummidock/penumocat`

##### Using GitHub (build docker image)

1) `git clone https://github.com/B-UMMI/docker-images.git`
2) `docker build -t pneumocat ./docker-images/pneumocat/`

### Run (using automated build image)
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/fastq_data:/data/ ummidock/pneumocat PneumoCaT.py -1 /path/to/sample_1.fastq.gz -2 /path/to/sample_2.fastq.gz


Contact
-------
Catarina Mendes <cimendes@medicina.ulisboa.pt>