# Build with: ./mk
FROM ubuntu:cosmic
MAINTAINER Titto Assini <tittoassini@gmail.com>

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y curl libtinfo-dev

# # Set the locale
RUN apt-get install -y locales;locale-gen en_US.UTF-8  
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8

#RUN locale

#RUN echo "export PATH=$PATH:/root/.local/bin" >> /root/.profile
#RUN export PATH=$PATH:/root/.local/bin

ENV PATH=/root/.local/bin:$PATH

#RUN cat /root/.profile

RUN curl -sSL https://get.haskellstack.org/ | sh

