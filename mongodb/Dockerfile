FROM ubuntu:19.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt-get update
RUN apt-get -y install curl
RUN mkdir -p mongo && curl -sL http://fastdl.mongodb.org/linux/mongodb-linux-x86_64-4.2.1.tgz | tar -xz --strip 1 -C mongo && cd mongo && cp -R bin /usr/local/ && mkdir -p /var/lib/mongo && cd ../ && rm -fR mongo
EXPOSE 27017
ENTRYPOINT 	["/usr/local/bin/mongod"]
