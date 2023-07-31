FROM ubuntu:22.04
MAINTAINER Makoto Kato <m_kato@ga2.so-net.ne.jp>

ADD sources.list /etc/apt/
ENV DEBIAN_FRONTEND=noninteractive
RUN dpkg --add-architecture armhf && \
    apt-get update && \
    apt-get install -y clang g++ mercurial g++-arm-linux-gnueabihf curl gyp ninja-build make python-is-python3 libssl-dev zlib1g-dev nodejs build-essential libpython3-dev m4 unzip zip uuid git python3-pip && \
    apt-get install -y zlib1g-dev:armhf libssl-dev:armhf libffi-dev:armhf libasound2-dev:armhf libcurl4-openssl-dev:armhf libdbus-1-dev:armhf libdbus-glib-1-dev:armhf libdrm-dev:armhf libgtk-3-dev:armhf libpulse-dev:armhf libx11-xcb-dev:armhf libxt-dev:armhf xvfb:armhf libstdc++-10-dev:armhf llvm && \
    apt-get clean
WORKDIR /root
ENV PATH="/root/.cargo/bin:${PATH}"
RUN curl https://sh.rustup.rs -s -o install.sh && sh install.sh -y && rm install.sh && rustup target add armv7-unknown-linux-gnueabihf
