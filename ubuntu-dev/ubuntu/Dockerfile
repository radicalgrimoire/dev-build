FROM ubuntu:focal

LABEL maintainer "ueno.s <ueno.s@gamestudio.co.jp>"

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
    && apt-get update -y \
    && apt-get upgrade -y \
    && apt-get install -y wget gnupg less language-pack-ja-base language-pack-ja tzdata curl jq git openssl sudo vim unzip cron logrotate init systemd
