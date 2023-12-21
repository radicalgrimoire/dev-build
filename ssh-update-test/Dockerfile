FROM ubuntu:focal
LABEL maintainer "ueno.s <ueno.s@gamestudio.co.jp>"

# Install required dependencies
RUN apt-get update && apt-get install -y \
    wget \
    build-essential \
    zlib1g-dev \
    && rm -rf /var/lib/apt/lists/*

# Download, compile, and install OpenSSH
WORKDIR /usr/local/src
RUN wget http://mirror.exonetric.net/pub/OpenBSD/OpenSSH/portable/openssh-9.6p1.tar.gz \
    && tar -zxvf openssh-9.6p1.tar.gz \
    && rm openssh-9.6p1.tar.gz

WORKDIR /usr/local/src/openssh-9.6p1
RUN ./configure \
    && make \
    && make install

# Create a symbolic link to the new ssh binary
RUN mv /usr/bin/ssh /usr/bin/ssh_old \
    && ln -s /usr/local/bin/ssh /usr/bin/ssh

# Verify the installed version of OpenSSH
RUN ssh -V