# docker-stacks

[![dockeri.co](https://dockeri.co/image/ummidock/stacks)](https://hub.docker.com/r/ummidock/stacks)
[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/stacks/)

Docker container with [Stacks](http://catchenlab.life.illinois.edu/stacks/) software.

[**Stacks**](http://catchenlab.life.illinois.edu/stacks/):

> Stacks is a software pipeline for building loci from short-read sequences, such as those generated on the Illumina platform.

> Stacks was developed to work with restriction enzyme-based data, such as RAD-seq, for the purpose of building genetic maps and conducting population genomics and phylogeography.

> Stacks is designed as a modular pipeline to efficiently curate and assemble large numbers of short-read sequences from multiple samples. Stacks identifies loci in a set of individuals, either de novo or aligned to a reference genome (including gapped alignments), and then genotypes each locus.

## Usage

You can download and run this image using the following commands:

````bash
# Pull
docker pull ummidock/stacks:2.53-01

# Run
docker run --rm -u $(id -u):$(id -g) -v /local/folder/data:/data/ ummidock/stacks:2.53-01 denovo_map.pl -T 8 -M 6 -o /data/stacks_output/ --samples /data/samples_fastq/ --popmap /data/population_map.tab --paired
````

For more examples on how to use **Stacks** please check the [manual](http://catchenlab.life.illinois.edu/stacks/manual/) page.

## Docker file
Docker file can be found [here](https://github.com/B-UMMI/docker-images/tree/master/stacks).

## Citation

Please cite one or both of these papers:

  * J. Catchen, P. Hohenlohe, S. Bassham, A. Amores, and W. Cresko. Stacks: an analysis tool set for population genomics. Molecular Ecology. 2013.
  * J. Catchen, A. Amores, P. Hohenlohe, W. Cresko, and J. Postlethwait. Stacks: building and genotyping loci de novo from short-read sequences. G3: Genes, Genomes, Genetics, 1:171-182, 2011.
