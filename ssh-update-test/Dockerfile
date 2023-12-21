FROM ubuntu:focal
LABEL maintainer "ueno.s <ueno.s@gamestudio.co.jp>"

RUN apt-get upgrade -y && apt-get update -y && apt-get install -y \
    sudo \
    build-essential zlib1g-dev libssl-dev libpam0g-dev libselinux1-dev libkrb5-dev \
    zlib1g-dev \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Download, compile, and install OpenSSL
WORKDIR /usr/local/src
RUN wget https://www.openssl.org/source/openssl-3.2.0.tar.gz \
    && tar -zxvf openssl-3.2.0.tar.gz \
    && rm openssl-3.2.0.tar.gz

WORKDIR /usr/local/src/openssl-3.2.0
RUN ./config \
    && make \
    && make install \
    && ldconfig

RUN which openssl
RUN openssl version

# Verify the installed version of OpenSSH
RUN ssh -V