# ./mk
FROM i386/ubuntu
MAINTAINER Titto Assini <tittoassini@gmail.com>

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

# # Set the locale
RUN apt-get install -y locales;locale-gen en_US.UTF-8  
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8
ENV PATH=/root/.cabal/bin:$PATH

RUN apt-get install -y curl libtinfo-dev git software-properties-common libz-dev

ENV CABALVER=2.4
ENV GHCVER=8.4.4
ENV PATH=/opt/ghc/$GHCVER/bin:/opt/cabal/$CABALVER/bin:$PATH

RUN add-apt-repository -y ppa:hvr/ghc;apt-get update

RUN apt-get -y install cabal-install-$CABALVER ghc-$GHCVER 

#ENV PATH=$PATH:/opt/ghc/bin

RUN cabal v2-update

RUN git clone https://github.com/Quid2/flat
RUN cd flat;cabal v2-configure -w ghc-8.4.4;cabal v2-build --only-dependencies
RUN cd flat;cabal v2-build --enable-tests
#RUN cd flat;cabal sandbox init;cabal install --only-dependencies --enable-tests
#RUN cd flat;cabal test
#RUN rm -rf flat
# RUN cabal update;cabal --version;cabal install Cabal cabal-install;cabal --version;
