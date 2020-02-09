ARG MINECRAFT_VERSION=1.15.2
FROM kitematic/minecraft:latest

MAINTAINER "ZeroC0D3 <zeroc0d3.team@gmail.com>"

ENV MINECRAFT_VERSION=${MINECRAFT_VERSION}

COPY rootfs/ /
WORKDIR /data
VOLUME [/data]
EXPOSE 25565/tcp

CMD ["/bin/sh","-c","echo eula=true > /data/eula.txt && java -jar /data/minecraft_server.${MINECRAFT_VERSION}.jar"]