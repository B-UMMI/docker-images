FROM ubuntu:22.04
MAINTAINER UMMI, imm-bioinfo@medicina.ulisboa.pt

# Create directory to store files
WORKDIR /WORKY/

# Install wget to download files
RUN apt update && apt install -y wget

# Download AGC executable
RUN wget https://github.com/refresh-bio/agc/releases/download/v3.0/agc-3.0_x64-linux.tar.gz
# Uncompress file
RUN tar -xf agc-3.0_x64-linux.tar.gz && rm agc-3.0_x64-linux.tar.gz
# Change permissions
RUN chmod +x agc-3.0_x64-linux/agc
# Add executable to the PATH
ENV PATH="/WORKY/agc-3.0_x64-linux:${PATH}"
