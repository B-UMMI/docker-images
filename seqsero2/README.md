# docker-seqsero2

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/seqsero2/)

Docker image with **SeqSero2** software ([GitHub page](https://github.com/denglab/SeqSero2)).

**SeqSero2**
> "SeqSero2 is a pipeline for Salmonella serotype determination from raw sequencing reads or genome assemblies.". From [here](https://github.com/denglab/SeqSero2).

---

## Usage

You can download and run this image using the following commands:
```bash
# Get Docker image
docker pull ummidock/seqsero2:alpha-test-1

# Run SeqSero2 in K-mer mode using reads
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/seqsero2:alpha-test-1 SeqSero2_package.py -p 1 -t 2 -i /data/sample_1.fastq.gz /data/sample_2.fastq.gz -d /data/out_kmer_reads
```
More examples on how to use **SeqSero2** (outside a Docker container context) can be found in **SeqSero2** [GitHub page](https://github.com/denglab/SeqSero2)

---

## Image Content

This Docker image contains:
* [SRA Toolkit](https://trace.ncbi.nlm.nih.gov/Traces/sra/sra.cgi?view=toolkit_doc) v2.9.1
* [SalmID](https://github.com/hcdenbakker/SalmID) v0.11
* [Biopython](https://biopython.org/) v1.71
* [BWA](http://bio-bwa.sourceforge.net/) v0.7.17-r1188
* [Samtools](http://www.htslib.org/) v1.7
* [Blast](https://blast.ncbi.nlm.nih.gov/Blast.cgi) v2.6.0+
* [SPAdes](http://cab.spbu.ru/software/spades/) v3.12.0
* [Bedtools](http://bedtools.readthedocs.io/en/latest/) v2.27.1

---

## Citation

If you use **SeqSero2** in your research, please cite:
> Zhang S, Yin Y, Jones MB, Zhang Z, Deatherage Kaiser BL, Dinsmore BA, Fitzgerald C, Fields PI, Deng X. Salmonella serotype determination utilizing high-throughput genome sequencing data. J Clin Microbiol. 2015 May;53(5):1685-92. doi: 10.1128/JCM.00323-15. Epub 2015 Mar 11. PubMed PMID: 25762776; PubMed Central PMCID: PMC4400759.

If you use **SeqSero2** using this Docker image, please add:
> SeqSero2 was run using the Docker image “ummidock/seqsero2:alpha-test-1” (https://hub.docker.com/r/ummidock/seqsero2/)
