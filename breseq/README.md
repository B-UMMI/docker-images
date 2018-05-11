# docker-breseq

[![Docker Automated buil](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/ummidock/breseq/)

Docker image with [**breseq**](http://barricklab.org/twiki/bin/view/Lab/ToolsBacterialGenomeResequencing) software ([GitHub page](https://github.com/barricklab/breseq)).

**breseq**
> "breseq is a computational pipeline for finding mutations relative to a reference sequence in short-read DNA re-sequencing data. It is intended for haploid microbial genomes (<20 Mb).". From [here](https://github.com/barricklab/breseq).

---

## Usage

You can download and run this image using the following commands:
```bash
# Get Docker image
docker pull ummidock/breseq:0.32.1

# Run sistr_cmd
docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/breseq:0.32.1 breseq --reference /data/reference1.gbk --name sample -j 1 --output /data/breseq_out/sample/ /data/sample_1.fastq.gz /data/sample_2.fastq.gz
```
More examples on how to use **breseq** (outside a Docker container context) can be found in **breseq** [manual page](http://barricklab.org/twiki/pub/Lab/ToolsBacterialGenomeResequencing/documentation/index.html)

---

## Image Content

This Docker image contains:
* [Bowtie2](http://bowtie-bio.sourceforge.net/bowtie2/index.shtml) v2.3.4.1
* [R](https://www.r-project.org/) v3.2.3
* [breseq](http://barricklab.org/twiki/bin/view/Lab/ToolsBacterialGenomeResequencing) v0.32.1

---

## Citation

If you use **breseq** in your research, please cite:
> Deatherage, D.E., Barrick, J.E. (2014) Identification of mutations in laboratory-evolved microbes from next-generation sequencing data using breseq. Methods Mol. Biol. 1151: 165–188.

If you use structural variation (junction) predictions, please cite:
> Barrick, J.E., Colburn, G., Deatherage D.E., Traverse, C.C., Strand, M.D., Borges, J.J., Knoester, D.B., Reba, A., Meyer, A.G. (2014) Identifying structural variation in haploid microbial genomes from short-read resequencing data using breseq. BMC Genomics 15:1039.
