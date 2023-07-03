FROM openjdk:jre-alpine

LABEL org.opencontainers.image.authors="jouni.tuominen@aalto.fi"

ENV SBT_VERSION 0.13.15

ENV SCALA_VERSION 2.11.5

RUN apk add --no-cache bash git curl && \
    curl -sL "https://github.com/sbt/sbt/releases/download/v$SBT_VERSION/sbt-$SBT_VERSION.tgz" | gunzip | tar -x -C /usr/local && \
    ln -s /usr/local/sbt/bin/sbt /usr/local/bin/sbt && \
    chmod 0755 /usr/local/bin/sbt && \
    rm -rf /var/cache/apk/*

WORKDIR /app

RUN git clone https://github.com/jiemakel/anything2rdf.git .

RUN sed -i "s/scalaVersion.*/scalaVersion := \"$SCALA_VERSION\"/g" build.sbt && \
    echo "baseDirectory in run := file(\"data\")" >> build.sbt

COPY run run.sh

ENTRYPOINT [ "sh" ]
CMD [ "run.sh" ]