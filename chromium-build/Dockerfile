FROM ubuntu:20.04
MAINTAINER Makoto Kato <m_kato@ga2.so-net.ne.jp>

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y git sudo lsb-release wget sed tzdata
WORKDIR /root
RUN git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
ENV PATH $PATH:/root/depot_tools
RUN wget https://raw.githubusercontent.com/chromium/chromium/master/build/install-build-deps-android.sh && chmod +x install-build-deps-android.sh
RUN wget https://raw.githubusercontent.com/chromium/chromium/master/build/install-build-deps.sh && chmod +x install-build-deps.sh
RUN sed -i 's/snapcraft/dummpfile/' install-build-deps.sh
RUN bash install-build-deps-android.sh
