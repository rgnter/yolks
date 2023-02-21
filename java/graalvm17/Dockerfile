FROM        --platform=$TARGETOS/$TARGETARCH ghcr.io/graalvm/jdk:ol9-java17
LABEL       author="Maros Prejsa" maintainer="maros.prejsa-1@gmail.com"
LABEL       org.opencontainers.image.source="https://github.com/rgnter/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         microdnf upgrade --assumeyes

USER        container
ENV         USER=container HOME=/home/container
ENV         JAVA_TOOL_OPTIONS="-Dfile.encoding=UTF-8 -Dsun.stderr.encoding=UTF-8 -Dsun.stdout.encoding=UTF-8"

WORKDIR     /home/container
COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
