# docker-blast+

Docker container with a [Blast+](https://blast.ncbi.nlm.nih.gov/Blast.cgi) software binaries.  
For LOBO cluster performance testing **ONLY**.

Usage
-----

    shifterimg pull ummidock/blast_binaries:2.6.0-binaries
    shifter --image=ummidock/blast_binaries:2.6.0-binaries blastn -help
