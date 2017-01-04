FROM ubuntu:zesty-20161129.1
MAINTAINER Luis Gonzalez <langelog@me.com>

ENV DEBIAN_FRONTEND noninteractive

RUN mkdir /app

WORKDIR /app

# updating base repo
RUN apt update
RUN apt upgrade -y

# allowing to install other repos
RUN apt install software-properties-common -y

# adding oracle repo
RUN add-apt-repository ppa:webupd8team/java -y

# updating repos
RUN apt update

# signing agreement for oracle certificates
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections

# installing JDK 8
RUN apt install oracle-java8-installer -y


# setting main command for image usage
CMD /bin/bash

