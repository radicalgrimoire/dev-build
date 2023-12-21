FROM ubuntu:focal
LABEL maintainer "ueno.s <ueno.s@gamestudio.co.jp>"

RUN apt-get update && apt-get install -y \
    openssh-server \
    && rm -rf /var/lib/apt/lists/*

RUN ssh -V