FROM ubuntu:19.10
MAINTAINER Shawn Jonnet <sjonnet@gmail.com>
RUN apt update
RUN apt install -y curl
RUN mkdir -p mongo && curl -sL https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-ubuntu1804-4.2.5.tgz | tar -xz --strip 1 -C mongo && cd mongo && cp -R bin /usr/local/ && cd ../ && mkdir -p /var/lib/mongo && rm -fR mongo
EXPOSE 27017
ENTRYPOINT 	["/usr/local/bin/mongod"]
