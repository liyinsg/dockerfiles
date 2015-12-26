# docker run --rm -v $HOME/webrtc:/home/build/webrtc -v $HOME/.ccache:/home/build/.ccache webrtc
FROM ubuntu
MAINTAINER Li Yin <liyin@live.com>

RUN apt-get update && apt-get install -y g++ python libnss3-dev libasound2-dev \
	libpulse-dev libjpeg62-dev libxv-dev libgtk2.0-dev libexpat1-dev git \
	openjdk-7-jre openjdk-7-jdk ant ccache \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN apt-get update && apt-get install -y lib32stdc++6 lib32z1 \
	&& apt-get clean && rm -fr /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN adduser --disabled-password --gecos "" build

RUN git clone --depth=1 \
	https://chromium.googlesource.com/chromium/tools/depot_tools.git \
	/opt/depot_tools && chown -R build:build /opt/depot_tools

ADD build /home/build/build
RUN chmod a+x /home/build/build

USER build
WORKDIR /home/build/webrtc
ENV PATH /opt/depot_tools:/usr/lib/ccache:$PATH
ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64
ENV GYP_DEFINES "OS=android build_with_libjingle=1 build_with_chromium=0 libjingle_java=1 enable_tracing=0"
CMD ["/home/build/build"]
