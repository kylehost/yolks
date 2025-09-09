FROM        --platform=$TARGETOS/$TARGETARCH adoptopenjdk/openjdk11:alpine-jre

LABEL       author="Kyle Speight" maintainer="kylw@kyle-hosting.xyz"

LABEL       org.opencontainers.image.source="https://github.com/kylehost/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache python3 py3-tz ca-certificates curl fontconfig git openssl sqlite tar tzdata \
			    && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
