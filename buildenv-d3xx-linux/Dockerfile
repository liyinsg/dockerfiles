# Build environment based on Ubuntu 14.04

FROM ubuntu:14.04
MAINTAINER Li Yin <yin.li@ftdichip.com>
RUN sed -i 's/archive.ubuntu.com/mirror.0x.sg/g' /etc/apt/sources.list && \
	apt-get update && apt-get -y install git-core g++-multilib make libc6-dev libtool automake && \
	apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*; \
	adduser --disabled-password --gecos "" build && echo "build:build" | chpasswd

USER build
WORKDIR /home/build
