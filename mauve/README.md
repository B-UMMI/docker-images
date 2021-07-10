# docker-snippy_tseemann

Docker container with [Mauve](http://darlinglab.org/mauve/mauve.html) software.

Usage
-----

You can download and run this image using the following commands:

    docker pull ummidock/mauve:2015-02-13

    # For GUI
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/mauve:2015-02-13 Mauve
    # For reordering contigs from the command-line (use fasta references)
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/mauve:2015-02-13 mauve_contigOrderer -output /data/results_dir/ -ref /data/reference.fasta -draft /data/contigs.fasta
