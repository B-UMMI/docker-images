FROM ubuntu:22.04
MAINTAINER UMMI, imm-bioinfo@medicina.ulisboa.pt

# Create directory to store files
WORKDIR /WORKY/

# Install wget to download files
RUN apt update && apt install -y wget

# Download Skani executable
RUN wget https://github.com/bluenote-1577/skani/releases/download/latest/skani
# Change permissions
RUN chmod +x skani
# Add executable to the PATH
ENV PATH="/WORKY:${PATH}"
