FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/graalvm/jdk:22.3.1
LABEL       author="Maros Prejsa" maintainer="maros.prejsa1@gmail.com"

LABEL       org.opencontainers.image.source="https://github.com/rgnter/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update -y \
						&& apt install -y curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 \
						&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
