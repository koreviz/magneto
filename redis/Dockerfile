FROM ubuntu:19.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt update
RUN apt install -y curl build-essential libssl-dev
RUN mkdir -p redis && curl -sL http://download.redis.io/releases/redis-5.0.8.tar.gz | tar -xz --strip 1 -C redis && cd redis && make && make install && cd ../ && mkdir -p /var/lib/redis && rm -fR redis
EXPOSE 6379
ENTRYPOINT ["/usr/local/bin/redis-server"]
