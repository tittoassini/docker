FROM agocorona/ghcjs

RUN cabal update

RUN git clone https://github.com/Quid2/flat

RUN cd flat;cabal --ghcjs new-build --dependencies-only

RUN cd flat;cabal --ghcjs new-build

RUN cd flat;git pull;cabal --ghcjs new-test spec

RUN rm -r flat

# increase to bust cache
ARG CACHEBUST=1 

# uncomment to update  
# RUN cd flat;git pull;cabal --ghcjs new-test spec

# check versions
#RUN cabal --version;ghcjs --version

