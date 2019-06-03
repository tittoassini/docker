# docker build -t quid2/x32-ubuntu-cabal .
FROM i386/ubuntu
MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y git ghc cabal-install

RUN cabal update

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal install --only-dependencies --enable-tests

RUN cd flat;cabal test

RUN rm -rf flat
