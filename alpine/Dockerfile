FROM node:10-alpine

RUN apk add --no-cache --virtual .pipeline-deps readline linux-pam \
        && apk add bash sudo shadow mediainfo sqlite-libs \
        ca-certificates \
        # Mono build dependencies (for libMonoPosixHelper.so)
        autoconf \
        automake \
        cmake \
        libtool \
        alpine-sdk \
        # .NET Core dependencies
        krb5-libs \
        icu-libs \
        libgcc \
        libintl \
        libssl1.1 \
        libstdc++ \
        zlib \
        && apk del .pipeline-deps

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/local/bin/node"

ENV \
    DOTNET_RUNNING_IN_CONTAINER=true

CMD [ "node" ]
