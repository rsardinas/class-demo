FROM mariadb
LABEL description="Mariadb Container for hw2"
MAINTAINER Rodrigo Sardinas <rodrigo.sardinas@auburn.edu>

EXPOSE 3306

ENV MARIADB_ROOT_PASSWORD="password" \
	MARIADB_DATABASE="demo"

COPY ./CreateTable.sql /docker-entrypoint-initdb.d/
