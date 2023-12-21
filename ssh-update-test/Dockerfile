FROM ubuntu:focal
LABEL maintainer "ueno.s <ueno.s@gamestudio.co.jp>"

# Install required dependencies
RUN apt-get update && apt-get install -y \
    wget \
     build-essential zlib1g-dev libssl-dev libpam0g-dev libselinux1-dev libkrb5-dev \
    zlib1g-dev \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

RUN which openssl