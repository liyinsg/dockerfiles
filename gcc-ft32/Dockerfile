#docker run -it --rm -v $PWD:/home/build liyin/gcc-ft32
FROM ubuntu:16.04
MAINTAINER Li Yin <liyin@live.com>

RUN apt-get update && apt-get install -y git lzip curl \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN apt-get update && apt-get build-dep -y gcc-avr binutils-avr \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD compile /root/
RUN bash /root/compile

RUN apt-get remove --purge -y ca-certificates curl ifupdown \
iproute2 isc-dhcp-client isc-dhcp-common krb5-locales less lzip \
netbase openssh-client openssl rename rsync xauth \
autopoint autotools-dev binutils binutils-avr bison bsdmainutils build-essential \
bzip2 cpp cpp-5 debhelper dh-autoreconf dh-python dh-strip-nondeterminism \
distro-info-data dpkg-dev file flex g++ g++-5 gawk gcc gcc-5 gettext gettext-base \
groff-base intltool-debian linux-libc-dev lsb-release m4 man-db mime-support \
patchutils po-debconf python3 python3-minimal python3.5 python3.5-minimal tex-common \
texinfo ucf xz-utils zlib1g-dev libx11-6 libx11-data libxcb1 && \
apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN adduser --disabled-password --gecos "" build
USER build
WORKDIR /home/build
ENV PATH /usr/local/opt/ft32/bin:$PATH
