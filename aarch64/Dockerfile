# docker build -t quid2/aarch64-ubuntu-cabal . 
# docker build  --build-arg CACHE_DATE="$(date)" -t quid2/armv7l-ubuntu-cabal . 
FROM balenalib/aarch64-ubuntu:20200221
MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN [ "cross-build-start" ]

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y git ghc cabal-install

RUN cabal update

RUN git clone https://github.com/Quid2/flat

# FAILS: cannot compile some dependencies
RUN cd flat;cabal install

RUN cd flat;cabal install --only-dependencies --enable-tests

RUN cd flat;cabal test

RUN rm -rf flat

# ARG CACHE_DATE

# RUN git clone https://github.com/Quid2/flat

# RUN cd flat;cabal install --only-dependencies --enable-tests

# RUN cd flat;cabal test

# RUN uname -a;ghc --version;cabal --version

RUN [ "cross-build-end" ]

# Questo venerdi dovrebbe andare a vedere la casa un'altra persona interessata, tramite un'altra agenzia, quindi vogliamo aspettare qualche giorno prima di prendere una decisione.