FROM ubuntu:22.04
MAINTAINER UMMI, imm-bioinfo@medicina.ulisboa.pt

# Create directory to store files
WORKDIR /WORKY/

# Install wget to download files, git to clone repos and Python 3 to install and use chewBBACA
RUN apt update && apt install -y wget

# Download Skani executable
RUN wget https://github.com/bluenote-1577/skani/releases/download/latest/skani
# Change permissions
RUN chmod +x skani
# Add executable to the PATH
ENV PATH="/WORKY:${PATH}"
