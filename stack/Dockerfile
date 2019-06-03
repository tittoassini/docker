# Build with: ./mk
FROM ubuntu:cosmic
MAINTAINER Titto Assini <tittoassini@gmail.com>

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y curl

#RUN echo "export PATH=$PATH:/root/.local/bin" >> /root/.profile

#RUN export PATH=$PATH:/root/.local/bin

ENV PATH=$PATH:/root/.local/bin

#RUN cat /root/.profile

RUN curl -sSL https://get.haskellstack.org/ | sh

# RUN stack test flat --resolver lts-6.35

# RUN stack test flat --resolver lts-9.21

# RUN stack test flat --resolver lts-11.22

# RUN stack test flat --resolver lts-12.19

# RUN stack test flat --resolver nightly-2018-11-18

# RUN git clone https://github.com/Quid2/flat

# RUN cd flat;for r in lts-6.35; do stack test --dependencies-only --resolver $r;done

# # RUN cd flat;for r in lts-6.35 lts-9.21 lts-11.22 lts-12.19 nightly-2018-11-18; do stack test --dependencies-only --resolver $r;done

# RUN rm -rf flat
