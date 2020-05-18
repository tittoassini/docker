# docker build -t quid2/armv7l-ubuntu-cabal . 
# run tests
# docker build  --build-arg CACHE_DATE="$(date)" -t quid2/armv7l-ubuntu-cabal . 
ARG BASE

FROM $BASE

MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN [ "cross-build-start" ]

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

RUN apt-get install -y git ghc cabal-install

RUN cabal update

RUN git clone https://github.com/Quid2/flat

# If we build in two stages (lib, then tests we end up recompiling a number of packages)
RUN cd flat;cabal install --only-dependencies --enable-tests

RUN cd flat;cabal build

RUN cd flat;cabal test

RUN rm -rf flat

ARG CACHE_DATE

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal configure --disable-optimization --ghc-options="-j +RTS -A128m -n2m -s -RTS"

# If we build in two stages (lib, then tests we end up recompiling a number of packages)
RUN cd flat;cabal install --only-dependencies --enable-tests

RUN cd flat;cabal build

RUN cd flat;cabal test

RUN uname -a;ghc --version;cabal --version

RUN [ "cross-build-end" ]