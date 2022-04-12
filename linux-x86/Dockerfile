FROM ubuntu:20.04

RUN dpkg --add-architecture i386 && \
    apt update && \
    apt install -y \
    tzdata \
    curl \
    tar \
    jq \
    libc6:i386 \
    libgcc1:i386 \
    libgssapi-krb5-2:i386 \
    libicu66:i386 \
    libssl1.1:i386 \
    libstdc++6:i386 \
    zlib1g:i386 \
    libsqlite3-0:i386 && \
    rm -rf /var/lib/apt/lists/* && \
    mkdir /opt/dotnet && \
    chown 1001 /opt/dotnet

ENV DOTNET_RUNNING_IN_CONTAINER=true DOTNET_ROOT=/opt/dotnet PATH="${PATH}:/opt/dotnet"

CMD [ "node" ]
