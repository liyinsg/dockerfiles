FROM ubuntu:16.04
MAINTAINER Li Yin <liyin@live.com>

RUN apt-get update && apt-get install -y git lzip curl \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN apt-get update && apt-get build-dep -y gcc-avr binutils-avr \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD 0001-ft32-port.patch /root/
ADD compile /root/
RUN bash /root/compile
