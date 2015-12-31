#docker run -it --rm -v $PWD:/home/build liyin/gcc-ft32
FROM ubuntu:16.04
MAINTAINER Li Yin <liyin@live.com>

RUN apt-get update && apt-get install -y git lzip curl \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN apt-get update && apt-get build-dep -y gcc-avr binutils-avr \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD 0001-ft32-port.patch /root/
ADD compile /root/
RUN bash /root/compile

RUN apt-get remove --purge -y ca-certificates curl git git-man ifupdown \
iproute2 isc-dhcp-client isc-dhcp-common krb5-locales less libalgorithm-c3-perl \
libarchive-extract-perl libasn1-8-heimdal libatm1 libb-hooks-endofscope-perl \
libb-hooks-op-check-perl libbareword-filehandles-perl libbsd0 libcgi-fast-perl \
libcgi-pm-perl libclass-c3-perl libclass-c3-xs-perl libclass-method-modifiers-perl \
libclass-xsaccessor-perl libcpan-changes-perl libcpan-meta-perl libcurl3-gnutls \
libdata-optlist-perl libdata-perl-perl libdata-section-perl libdevel-caller-perl \
libdevel-globaldestruction-perl libdevel-lexalias-perl libdns-export100 libedit2 \
libencode-locale-perl liberror-perl libexpat1 libexporter-tiny-perl libfcgi-perl \
libffi6 libfile-slurp-perl libgdbm3 libgetopt-long-descriptive-perl libgmp10 \
libgnutls-deb0-28 libgssapi-krb5-2 libgssapi3-heimdal libhcrypto4-heimdal \
libheimbase1-heimdal libheimntlm0-heimdal libhogweed4 libhtml-parser-perl \
libhtml-tagset-perl libhttp-date-perl libhttp-message-perl libhx509-5-heimdal \
libidn11 libimport-into-perl libindirect-perl libio-html-perl libio-stringy-perl \
libirs-export91 libisc-export95 libisccfg-export90 libk5crypto3 libkeyutils1 \
libkrb5-26-heimdal libkrb5-3 libkrb5support0 libldap-2.4-2 \
liblexical-sealrequirehints-perl liblist-moreutils-perl liblog-message-perl \
liblog-message-simple-perl liblwp-mediatypes-perl libmodule-build-perl \
libmodule-implementation-perl libmodule-pluggable-perl libmodule-runtime-perl \
libmodule-signature-perl libmoo-perl libmoox-handlesvia-perl libmro-compat-perl \
libmultidimensional-perl libnamespace-autoclean-perl libnamespace-clean-perl \
libnettle6 libp11-kit0 libpackage-constants-perl libpackage-stash-perl \
libpackage-stash-xs-perl libpadwalker-perl libparams-classify-perl \
libparams-util-perl libparams-validate-perl libpath-tiny-perl libpod-latex-perl \
libpod-markdown-perl libpod-readme-perl libpopt0 libroken18-heimdal \
librole-tiny-perl librtmp1 libsasl2-2 libsasl2-modules libsasl2-modules-db \
libsoftware-license-perl libsqlite3-0 libssl1.0.0 libstrictures-perl \
libsub-exporter-perl libsub-exporter-progressive-perl libsub-identify-perl \
libsub-install-perl libsub-name-perl libtasn1-6 libterm-ui-perl \
libtext-soundex-perl libtext-template-perl libtimedate-perl libtry-tiny-perl \
libtype-tiny-perl libtype-tiny-xs-perl libunicode-utf8-perl liburi-perl \
libvariable-magic-perl libwind0-heimdal libx11-6 libx11-data libxau6 libxcb1 \
libxdmcp6 libxext6 libxmuu1 libxtables10 lzip netbase openssh-client openssl \
patch perl perl-modules rename rsync xauth autoconf autoconf2.64 automake1.11 \
autopoint autotools-dev binutils binutils-avr bison bsdmainutils build-essential \
bzip2 cpp cpp-5 debhelper dh-autoreconf dh-python dh-strip-nondeterminism \
distro-info-data dpkg-dev file flex g++ g++-5 gawk gcc gcc-5 gettext gettext-base \
groff-base intltool-debian libarchive-zip-perl libasan2 libasprintf0v5 libatomic1 \
libbison-dev libc-dev-bin libc6-dev libcc1-0 libcilkrts5 libcroco3 libdpkg-perl \
libfile-stripnondeterminism-perl libfl-dev libgcc-5-dev libglib2.0-0 libgmp-dev \
libgmpxx4ldbl libgomp1 libicu55 libintl-perl libisl15 libitm1 liblsan0 libmagic1 \
libmpc-dev libmpc3 libmpdec2 libmpfr-dev libmpfr4 libmpx0 libpipeline1 \
libpython3-stdlib libpython3.5-minimal libpython3.5-stdlib libquadmath0 \
libsigsegv2 libstdc++-5-dev libtext-unidecode-perl libtool libtsan0 libubsan0 \
libunistring0 libxml-libxml-perl libxml-namespacesupport-perl libxml-sax-base-perl \
libxml-sax-perl libxml2 linux-libc-dev lsb-release m4 make man-db mime-support \
patchutils po-debconf python3 python3-minimal python3.5 python3.5-minimal tex-common \
texinfo ucf xz-utils zlib1g-dev && \
apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN adduser --disabled-password --gecos "" build
USER build
WORKDIR /home/build
ENV PATH /usr/local/opt/ft32/bin:$PATH
