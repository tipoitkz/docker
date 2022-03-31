FROM openjdk:8-jre

WORKDIR /schemaspy

RUN apt-get update && \
    apt-get install -y --no-install-recommends graphviz git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN \
  wget https://github.com/schemaspy/schemaspy/releases/download/v6.1.0/schemaspy-6.1.0.jar -O schemaSpy.jar && \
  #wget --no-check-certificate https://schemaspy.org/schemaspy/schemaspy-6.1.1-SNAPSHOT.jar -O schemaSpy.jar && \
  wget https://jdbc.postgresql.org/download/postgresql-42.3.3.jar -O postgresql.jar

VOLUME /schemaspy/output

ENTRYPOINT [ "java", "-jar", "schemaSpy.jar", "-o", "output", "-dp", "postgresql.jar" ]

CMD [ "-host", "database", "-port", "5432", "-db", "postgres", "-u", "postgres", "-p", "postgres", "-t", "pgsql11" ]
