FROM ubuntu:21.04
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt update
RUN apt install -y curl
RUN mkdir -p mongo && curl -sL https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-ubuntu2004-4.4.6.tgz | tar -xz --strip 1 -C mongo && cd mongo && cp -R bin /usr/local/ && cd ../ && mkdir -p /var/lib/mongo && rm -fR mongo
EXPOSE 27017
ENTRYPOINT 	["/usr/local/bin/mongod"]
