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

RUN apt-get install -y curl libtinfo-dev git ghc cabal-install libz-dev

RUN cabal update;cabal --version;cabal install Cabal cabal-install;cabal --version;

RUN cabal --version

# RUN git clone https://github.com/Quid2/zm
# RUN cd zm;cabal sandbox init;cabal install --only-dependencies --enable-tests
#RUN cd zm;cabal test
#RUN rm -rf zm
