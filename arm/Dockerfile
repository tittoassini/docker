# docker build -t quid2/armv7l-ubuntu-cabal . 
# docker build  --build-arg CACHE_DATE="$(date)" -t quid2/armv7l-ubuntu-cabal . 
FROM resin/armv7hf-ubuntu
MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN [ "cross-build-start" ]

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y git ghc cabal-install

RUN cabal update

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal install --only-dependencies --enable-tests;cabal test

RUN rm -rf flat

ARG CACHE_DATE=NOW

RUN git clone https://github.com/Quid2/flat;cd flat;cabal install --only-dependencies --enable-tests;cabal test

RUN uname -a;ghc --version;cabal --version

RUN [ "cross-build-end" ]