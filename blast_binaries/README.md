# docker-blast+

Docker container with a [Blast+](https://blast.ncbi.nlm.nih.gov/Blast.cgi) software binaries.
For LOBO cluster performance testing.

Usage
-----

    shifterimg pull ummidock/blast:2.6.0-binaries
    shifter --image=ummidock/blast:2.6.0-binaries blastn -help
