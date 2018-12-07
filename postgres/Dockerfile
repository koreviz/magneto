FROM ubuntu:18.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN touch /etc/apt/sources.list.d/pgdg.list && echo "deb http://apt.postgresql.org/pub/repos/apt/ artful-pgdg main" | tee -a /etc/apt/sources.list.d/pgdg.list
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
RUN apt-get update
RUN apt-get -y install postgresql-11 postgresql-contrib-11
USER postgres
RUN echo "host all  all    0.0.0.0/0  md5" >> /etc/postgresql/11/main/pg_hba.conf
RUN echo "listen_addresses='*'" >> /etc/postgresql/10/main/postgresql.conf
EXPOSE 5432
VOLUME ["/etc/postgresql", "/var/log/postgresql", "/var/lib/postgresql"]
CMD ["/usr/lib/postgresql/11/bin/postgres", "-D", "/var/lib/postgresql/11/main", "-c", "config_file=/etc/postgresql/11/main/postgresql.conf"]
