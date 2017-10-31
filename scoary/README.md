Scoary - Docker
=============
Pan-genome wide association studies

<https://github.com/AdmiralenOla/Scoary>


This is a dockerfile for using Scoary, with the principal dependencies already installed (no GUI).

Within this container you can find:
- ubuntu:16.04
- Python-dev and pip
- ete3 six
- scoary

### Using play-with-docker
[![Try in PWD](https://cdn.rawgit.com/play-with-docker/stacks/cff22438/assets/images/button.png)](http://labs.play-with-docker.com/)

Within [play-with-docker](http://labs.play-with-docker.com/) webpage click on **create session**. Then, another page
will open with a big counter on the upper left corner. Click on **+ add new instance** and a terminal like instance should be generated on the right. On
this terminal you can load this docker image as follows:

`docker pull cimendes/scoary`

#### Build this docker on your local machine

For this, docker needs to be installed on your machine. Instructions for this can be found [here](https://docs.docker.com/engine/installation/).

##### Using DockerHub (automated build image)

`docker pull cimendes/scoary`

##### Using GitHub (build docker image)

1) `git clone https://github.com/B-UMMI/docker-images.git`
2) `docker build -t scoary ./docker-images/scoary/`

### Run (using automated build image)
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/fastq_data:/data/ cimendes/scoary scoary --test

Contact
-------
Catarina Mendes <cimendes@medicina.ulisboa.pt>