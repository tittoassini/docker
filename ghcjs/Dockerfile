FROM agocorona/ghcjs

RUN cabal update

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal --ghcjs new-build --dependencies-only 

RUN cd flat;cabal --ghcjs new-build

RUN cabal --ghcjs new-test spec --dependencies-only 

#RUN cabal --ghcjs new-test spec

#ARG CACHEBUST=1 # increase to bust cache

#RUN cd flat;git pull;cabal --ghcjs new-test spec

#RUN cabal --version;ghcjs --version

