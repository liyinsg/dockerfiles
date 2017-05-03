# Build environment based on Ubuntu 16.04
# docker run --it -v $HOME:/home/ly liyin/xenial

FROM ubuntu:16.04
MAINTAINER Li Yin <liyin@live.com>
RUN sed -i 's/archive.ubuntu.com/mirror.0x.sg/g' /etc/apt/sources.list; \
	apt-get update && apt-get -y install sudo; \
	apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*; \
	adduser --disabled-password --gecos "" ly && echo "ly:ly" | chpasswd && \
	adduser ly sudo

USER ly
WORKDIR /home/ly
