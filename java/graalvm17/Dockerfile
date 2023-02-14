FROM        --platform=$TARGETOS/$TARGETARCH alpine:3.14

LABEL       author="Maros Prejsa" maintainer="maros.prejsa-1@gmail.com"
LABEL       org.opencontainers.image.source="https://github.com/rgnter/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update -y \
				&& apt install -y curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 \
				&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container
COPY        ./../entrypoint.sh /entrypoint.sh

FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/graalvm/jdk:22.3.1

CMD         [ "/bin/bash", "/entrypoint.sh" ]
