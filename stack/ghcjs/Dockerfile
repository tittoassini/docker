# ./mk 9.21 ghcjs-0.2.1.9009021_ghc-8.0.2
FROM quid2/stack
# See also https://github.com/dplusic/docker-stack-ghcjs
MAINTAINER Titto Assini <tittoassini@gmail.com>

ARG STK

RUN apt-get install -y ncurses-dev

RUN apt-get install -y cabal-install alex

RUN apt-get install -y nodejs npm 
#  happy cpphs hscolour 
ARG VER

# cabal version might not suitable for all versions of ghcjs
# RUN stack install cabal-install-2.0.1.1 alex

ENV PATH=/root/.stack/programs/x86_64-linux/$VER/bin:$PATH

# RUN which cabal
# RUN cabal --version
# RUN cabal update;cabal install cabal-install
# RUN which cabal
# RUN cabal --version

RUN git clone https://github.com/Quid2/flat
RUN cd flat;stack test --dependencies-only --stack-yaml stack-ghcjs-$STK.yaml
RUN rm -rf flat
