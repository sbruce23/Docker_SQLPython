# dump build stage
FROM postgres:17.6 as dumper
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.4"
LABEL description="Postgres database"

RUN ["sed", "-i", "s/exec \"$@\"/echo \"skipping...\"/", "/usr/local/bin/docker-entrypoint.sh"]

ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=behappy
ENV PGDATA=/data
ENV POSTGRES_DB=sqlda

COPY datadump.sql /docker-entrypoint-initdb.d/

RUN chown -R postgres:postgres /docker-entrypoint-initdb.d/

RUN ["/usr/local/bin/docker-entrypoint.sh", "postgres"]

# final build stage
FROM postgres:17.6

COPY --from=dumper /data $PGDATA
