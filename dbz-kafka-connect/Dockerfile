FROM confluentinc/cp-kafka-connect:6.1.0

LABEL maintainer="Naren Ravilla"

ENV DBZ_CONNECTOR_POSTGRES=1.4.2

USER root

RUN wget "https://repo1.maven.org/maven2/io/debezium/debezium-connector-postgres/${DBZ_CONNECTOR_POSTGRES}.Final/debezium-connector-postgres-${DBZ_CONNECTOR_POSTGRES}.Final-plugin.tar.gz" && \
tar xfz $PWD/debezium-connector-postgres-${DBZ_CONNECTOR_POSTGRES}.Final-plugin.tar.gz -C $PWD && \
cp $PWD/debezium-connector-postgres/*.jar /usr/share/java/kafka/

COPY source-jdbc-postgres.properties /usr/etc/kafka-connect-jdbc