# Build environment based on MINGW

FROM ubuntu:latest
MAINTAINER Li Yin <yin.li@ftdichip.com>
RUN sed -i 's/archive.ubuntu.com/mirror.0x.sg/g' /etc/apt/sources.list && \
	apt-get update && apt-get -y install git-core make mingw-w64 libtool automake texlive-full pandoc && \
	apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*; \
	adduser --disabled-password --gecos "" build && echo "build:build" | chpasswd

USER build
WORKDIR /home/build
