FROM agocorona/ghcjs

RUN cabal update

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal --ghcjs new-build --dependencies-only 

# RUN cd flat;cabal --ghcjs new-build

#RUN cd flat;git pull;cabal new-test spec

# #ARG CACHEBUST=5

#RUN cabal --version;ghcjs --version

