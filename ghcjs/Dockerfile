FROM agocorona/ghcjs

RUN cabal update

RUN which cabal
RUN cabal --version

RUN ghc --version

RUN cabal update

RUN curl -k --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh

RUN ghcup install cabal

# RUN cabal install cabal-install
RUN which cabal
RUN cabal --version

# RUN git clone https://github.com/Quid2/flat;

#RUN cd flat;cabal --ghcjs new-build  --constraint "tasty -clock"


#RUN rm -r flat

ARG CACHE_DATE

RUN cabal --version

# RUN ghcjs --version

# RUN pwd

# RUN git clone https://github.com/Quid2/flat;cd flat;cabal --ghcjs new-build --enable-tests;node dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe/all.js;node dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/spec/build/spec/spec.jsexe/all.js


#RUN cd flat;cabal new-test --project-file cabal.project.ghcjs
#RUN cd flat;cabal --ghcjs new-build;cabal cabal --ghcjs new-test doc-static --constraint "tasty -clock"
#RUN cabal --configure --ghcjs
# RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe
# RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/spec/build/spec/spec.jsexe
# RUN cd flat;cabal --ghcjs new-test doc-static --constraint "tasty -clock"
# RUN cd flat;cabal --ghcjs new-test spec --constraint "tasty -clock"
# RUN cd flat;cabal --ghcjs new-build;cabal cabal --ghcjs new-test doc-static --constraint "tasty -clock"
#           /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4/t/doc-static/build/doc-static/doc-static.jsexe

# check versions


