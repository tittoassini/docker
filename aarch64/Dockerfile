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
# RUN cd flat;cabal install
# If we build in two stages (lib, then tests we end up recompiling a number of packages)
RUN cd flat;cabal install --enable-tests

RUN cd flat;cabal test

ARG CACHE_DATE

RUN cd flat;cabal test

RUN uname -a;ghc --version;cabal --version

# RUN git clone https://github.com/Quid2/flat

# RUN cd flat;cabal install --only-dependencies --enable-tests

# RUN cd flat;cabal test

RUN uname -a;ghc --version;cabal --version

# RUN [ "cross-build-end" ]

