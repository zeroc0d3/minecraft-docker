ARG MINECRAFT_VERSION=1.18.2
ARG MINECRAFT_FORGE_VERSION=40.0.32

# FROM openjdk:8u171-jdk-stretch
FROM openjdk:19-jdk-oracle

ARG BUILD_DATE
ARG BUILD_VERSION
ARG GIT_COMMIT
ARG GIT_URL

ENV VENDOR="DevOpsCornerId"
ENV AUTHOR="DevOpsCorner.id <support@devopscorner.id>"
ENV IMG_NAME="minecraft-server"
ENV IMG_VERSION="1.18.2"
ENV IMG_DESC="Minecraft Server"
ENV IMG_ARCH="amd64/x86_64"

LABEL maintainer="$AUTHOR" \
    architecture="$IMG_ARCH" \
    minecraft-version="$MINECRAFT_VERSION" \
    minecraft-forge-version="$MINECRAFT_FORGE_VERSION" \
    org.label-schema.build-date="$BUILD_DATE" \
    org.label-schema.name="$IMG_NAME" \
    org.label-schema.description="$IMG_DESC" \
    org.label-schema.vcs-ref="$GIT_COMMIT" \
    org.label-schema.vcs-url="$GIT_URL" \
    org.label-schema.vendor="$VENDOR" \
    org.label-schema.version="$BUILD_VERSION" \
    org.label-schema.schema-version="$IMG_VERSION" \
    org.opencontainers.image.authors="$AUTHOR" \
    org.opencontainers.image.description="$IMG_DESC" \
    org.opencontainers.image.vendor="$VENDOR" \
    org.opencontainers.image.version="$IMG_VERSION" \
    org.opencontainers.image.revision="$GIT_COMMIT" \
    org.opencontainers.image.created="$BUILD_DATE" \
    fr.hbis.docker.base.build-date="$BUILD_DATE" \
    fr.hbis.docker.base.name="$IMG_NAME" \
    fr.hbis.docker.base.vendor="$VENDOR" \
    fr.hbis.docker.base.version="$BUILD_VERSION"

ENV MINECRAFT_VERSION=${MINECRAFT_VERSION}
ENV MINECRAFT_FORGE_VERSION=${MINECRAFT_FORGE_VERSION}
ENV CMD_SERVER_MINECRAFT=/data/minecraft/minecraft_server.${MINECRAFT_VERSION}.jar
ENV CMD_SERVER_FORGE=/data/minecraft/forge-${MINECRAFT_VERSION}-${MINECRAFT_FORGE_VERSION}-launcher.jar
ENV CMD_SERVER=${CMD_SERVER_MINECRAFT}

COPY rootfs/ /
COPY docker-entrypoint.sh /

WORKDIR /data/minecraft
VOLUME [/data]
EXPOSE 25565/tcp

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["java", "-Xmx1024M", "-Xms1024M", "-jar", ${CMD_SERVER}, "nogui"]