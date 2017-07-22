# docker-kraken_metagenomics

Docker container with [Kraken](https://ccb.jhu.edu/software/kraken/) software.

Usage
-----

You can download and run this image using the following commands:

    # Get Docker image
    docker pull ummidock/kraken_metagenomics:0.10.5-beta

    # Analyse the data with minikraken DB
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:0.10.5-beta kraken --preload --fastq-input --db minikraken_20141208 --threads 2 --output /data/minikraken.sample.txt --paired --gzip-compressed /data/sample_1.fastq.gz /data/sample_2.fastq.gz

    # Get Kraken report
    docker run --rm -u $(id -u):$(id -g) -it -v /local/folder/data:/data/ ummidock/kraken_metagenomics:0.10.5-beta kraken-report --db minikraken_20141208 /data/minikraken.sample.txt > /data/minikraken.sample.report.txt
