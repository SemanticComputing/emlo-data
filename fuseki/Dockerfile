FROM secoresearch/fuseki

MAINTAINER Jouni Tuominen <jouni.tuominen@aalto.fi>

ENV EMLO_TTL /app/data/emlo.ttl

ENV EMLO_GRAPH http://ldf.fi/emlo/main/

COPY --chown=9008 load_data $FUSEKI_HOME/load_data.sh