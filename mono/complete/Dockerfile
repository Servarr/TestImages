FROM ubuntu:xenial

ENV DEBIAN_FRONTEND noninteractive
ARG MONO_VERSION=5.20
ARG MONO_URL=stable-xenial/snapshots/$MONO_VERSION

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF && \
    echo "deb http://download.mono-project.com/repo/debian $MONO_URL main" > /etc/apt/sources.list.d/mono-official-stable.list && \
    apt-get update && apt-get install -y \ 
        tzdata \
        mono-complete \
        sqlite3 \
        mediainfo \
        curl \
        tar \
        && rm -rf /var/lib/apt/lists/*

WORKDIR /data/
RUN curl -Lo chromaprint.tar.gz "https://github.com/acoustid/chromaprint/releases/download/v1.4.3/chromaprint-fpcalc-1.4.3-linux-x86_64.tar.gz" && \
        tar xf chromaprint.tar.gz --strip-components=1 --directory /usr/bin && \
        rm -r chromaprint*
