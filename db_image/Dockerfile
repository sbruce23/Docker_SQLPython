# dump build stage
FROM postgres:15.1 as dumper
LABEL maintainer="Scott A. Bruce <sabruce@tamu.edu>"
LABEL version="1.1"
LABEL description="Postgres database for STAT 624"

RUN ["sed", "-i", "s/exec \"$@\"/echo \"skipping...\"/", "/usr/local/bin/docker-entrypoint.sh"]

ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=behappy
ENV PGDATA=/data
ENV POSTGRES_DB=sqlda

COPY datadump.sql /docker-entrypoint-initdb.d/

RUN chown -R postgres:postgres /docker-entrypoint-initdb.d/

RUN ["/usr/local/bin/docker-entrypoint.sh", "postgres"]

# final build stage
FROM postgres:15.1

COPY --from=dumper /data $PGDATA

