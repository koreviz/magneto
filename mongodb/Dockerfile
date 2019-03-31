FROM ubuntu:18.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt-get update
RUN apt-get -y install curl
RUN mkdir -p mongo && curl -sL http://fastdl.mongodb.org/linux/mongodb-linux-x86_64-4.0.8.tgz | tar -xz --strip 1 -C mongo && cd mongo && cp -R bin /usr/local/ && mkdir -p /var/lib/mongo && cd ../ && rm -fR mongo
EXPOSE 27017
ENTRYPOINT 	["/usr/local/bin/mongod"]