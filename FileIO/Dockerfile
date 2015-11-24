FROM ubuntu:14.04
MAINTAINER  ravnee@ncsu.edu

RUN apt-get -y update
RUN apt-get -y install socat

RUN echo fileIOContainer > my.txt
CMD socat TCP-LISTEN:9000 SYSTEM:'cat my.txt'

