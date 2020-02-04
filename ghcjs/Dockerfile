FROM agocorona/ghcjs

RUN cabal new-update

RUN git clone https://github.com/Quid2/flat

#RUN cabal --version;ghcjs --version

RUN cd flat;cabal new-build --dependencies-only 
# #ARG CACHEBUST=5
# RUN cd flat;git pull;cabal new-test spec

