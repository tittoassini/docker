# Build with: ./mk lts-6.35
FROM quid2/stack
MAINTAINER Titto Assini <tittoassini@gmail.com>

ARG STK

RUN git clone https://github.com/Quid2/flat
RUN cd flat;stack test --dependencies-only --resolver $STK
RUN rm -rf flat

RUN apt-get install -y libtinfo-dev

RUN git  clone https://github.com/Quid2/model
RUN cd model;stack test --dependencies-only --resolver $STK
RUN rm -rf model

