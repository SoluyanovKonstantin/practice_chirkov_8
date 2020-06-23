FROM postgres:latest

WORKDIR /

ENV POSTGRES_PASSWORD postgres
ENV POSTGRES_USER postgres
ENV POSTGRES_DB name

RUN mkdir --parents /docker-entrypoint-initdb.d

COPY ./pg-init-scripts ./docker-entrypoint-initdb.d