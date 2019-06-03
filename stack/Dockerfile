# Build with: ./mk
FROM ubuntu:cosmic
MAINTAINER Titto Assini <tittoassini@gmail.com>

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y curl libtinfo-dev

#RUN echo "export PATH=$PATH:/root/.local/bin" >> /root/.profile

#RUN export PATH=$PATH:/root/.local/bin

ENV PATH=$PATH:/root/.local/bin

#RUN cat /root/.profile

RUN curl -sSL https://get.haskellstack.org/ | sh

