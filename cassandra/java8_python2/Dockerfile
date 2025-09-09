FROM        --platform=$TARGETOS/$TARGETARCH adoptopenjdk/openjdk8:alpine-jre

LABEL       author="Kyle Speight" maintainer="kyle@kyle-hosting.xyz"

LABEL       org.opencontainers.image.source="https://github.com/kylehost/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache python2 ca-certificates curl fontconfig git openssl sqlite tar tzdata \
				&& python -m ensurepip --upgrade && pip install pytz \
			    && adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
