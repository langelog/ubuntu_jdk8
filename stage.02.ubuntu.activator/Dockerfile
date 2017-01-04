FROM langelog/ubuntu_playframework:ubuntu_jdk8
MAINTAINER Luis Gonzalez <langelog@me.com>

ENV DEBIAN_FRONTEND noninteractive

# updating base repo
RUN apt update
RUN apt upgrade -y

# install unzip
RUN apt install unzip -y

# Download activator
RUN wget -c https://downloads.typesafe.com/typesafe-activator/1.3.12/typesafe-activator-1.3.12.zip

# Decompress it
RUN unzip typesafe-activator-1.3.12.zip
# Delete zip
RUN rm typesafe-activator-1.3.12.zip
# move to root directory
RUN mv activator-dist-1.3.12/ /root/activator
# registrate it to path
RUN echo "export PATH=/root/activator/bin:$PATH" >> $HOME/.profile
# make sure that activator is executable
RUN chmod u+x /root/activator/bin/activator

