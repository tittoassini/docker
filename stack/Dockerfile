# Build with: ./mk
FROM ubuntu:cosmic
MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN echo "北京市"

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

# # Set the locale
RUN apt-get install -y locales;locale-gen en_US.UTF-8  
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8

RUN locale


# RUN apt-get install -y curl libtinfo-dev



#RUN echo "export PATH=$PATH:/root/.local/bin" >> /root/.profile

#RUN export PATH=$PATH:/root/.local/bin

ENV PATH=$PATH:/root/.local/bin

#RUN cat /root/.profile

##RUN curl -sSL https://get.haskellstack.org/ | sh

