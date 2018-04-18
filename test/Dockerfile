# Version: 0.0.1
FROM ubuntu:17.10
MAINTAINER Zebulun Arendsee "zbwrnz@gmail.com"
RUN apt-get update
RUN apt-get install -y git
RUN git clone https://github.com/arendsee/dotfiles
EXPOSE 80

# to build:
# $ sudo docker build -t="arendsee/test:v0.0.1" .
