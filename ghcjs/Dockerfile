FROM agocorona/ghcjs

RUN cabal update

RUN which cabal
RUN cabal --version
RUN cabal update;cabal install cabal-install
RUN which cabal
RUN cabal --version

RUN git clone https://github.com/Quid2/flat;

RUN cd flat;cabal --ghcjs new-build --enable-tests

RUN rm -r flat

ARG CACHE_DATE

RUN git clone https://github.com/Quid2/flat;cd flat;cabal --ghcjs new-build --enable-tests;node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe/all.js;node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/spec/build/spec/spec.jsexe/all.js

#RUN cd flat;cabal new-test --project-file cabal.project.ghcjs
#RUN cd flat;cabal --ghcjs new-build;cabal cabal --ghcjs new-test doc-static --constraint "tasty -clock"
#RUN cabal --configure --ghcjs


# RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe

# RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/spec/build/spec/spec.jsexe


# RUN cd flat;cabal --ghcjs new-test doc-static --constraint "tasty -clock"

# RUN cd flat;cabal --ghcjs new-test spec --constraint "tasty -clock"

# RUN cd flat;cabal --ghcjs new-build;cabal cabal --ghcjs new-test doc-static --constraint "tasty -clock"
#           /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe
# 

# ARG CACHE_DATE


# RUN rm -r flat

# RUN cabal --version;ghcjs --version

# ARG CACHE_DATE


# ENV PATH=/root/.cabal:$PATH

# uncomment to update  
# RUN cd flat;git pull;cabal --ghcjs new-test spec

# check versions
#RUN cabal --version;ghcjs --version

