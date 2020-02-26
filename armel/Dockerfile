# docker build -t quid2/armel-debian-cabal . 
FROM resin/armel-debian
MAINTAINER Titto Assini <tittoassini@gmail.com>

RUN [ "cross-build-start" ]

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

# BUG this is still ghc7.6.3 so it cannot work
RUN apt-get install -y git ghc cabal-install

RUN cabal update

RUN git clone https://github.com/Quid2/flat

# # FAILS: cannot compile some dependencies
RUN cd flat;cabal install --only-dependencies --enable-tests;cabal test

RUN rm -rf flat

# # ARG CACHE_DATE

# # RUN git clone https://github.com/Quid2/flat;cd flat;cabal install --only-dependencies --enable-tests;cabal test

# # RUN uname -a;ghc --version;cabal --version

RUN [ "cross-build-end" ]