FROM ubuntu:17.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt-get update
RUN apt-get -y install curl build-essential libssl-dev
RUN mkdir -p redis && curl -sL http://download.redis.io/releases/redis-4.0.7.tar.gz | tar -xz --strip 1 -C redis && cd redis && make && make install && cd ../ && mkdir -p /var/lib/redis && rm -fR redis
EXPOSE 6379
ENTRYPOINT ["/usr/local/bin/redis-server"]