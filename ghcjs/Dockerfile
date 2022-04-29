FROM agocorona/ghcjs

RUN cabal update

RUN which cabal
RUN cabal --version

RUN ghc --version

RUN cabal update

RUN apt-get install -y build-essential curl libffi-dev libffi6 libgmp-dev libgmp10 libncurses-dev libncurses5 libtinfo5

ENV PATH=/root/.ghcup/bin:/root/.cabal/bin:$PATH

RUN mkdir -p /root/.ghcup/bin; curl https://downloads.haskell.org/~ghcup/x86_64-linux-ghcup --output /root/.ghcup/bin/ghcup;chmod u+x /root/.ghcup/bin/ghcup

RUN ghcup install cabal
RUN ghcup list
RUN which cabal

RUN cabal --version
RUN ghcjs --version
RUN ghc --version

RUN git clone https://github.com/Quid2/flat;

RUN cd flat;cabal --ghcjs new-build  --constraint "tasty -clock"

RUN apt-get install nodejs

RUN cd flat;cabal --ghcjs new-build  --constraint "tasty -clock"

RUN cd flat;cabal build --enable-tests --ghcjs --constraint "tasty -clock" flat:repr
RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4.5/t/repr/build/repr/repr.jsexe/all.js

RUN cd flat;cabal build --enable-tests --ghcjs --constraint "tasty -clock" flat:doc-static
RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4.5/t/doc-static/build/doc-static/doc-static.jsexe/all.js

RUN cd flat;cabal build --enable-tests --ghcjs --constraint "tasty -clock" flat:ghcjs-cons
RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4.5/t/ghcjs-cons/build/ghcjs-cons/ghcjs-cons.jsexe/all.js

RUN cd flat;cabal build --enable-tests --ghcjs --constraint "tasty -clock" flat:spec
RUN node /opt/flat/dist-newstyle/build/x86_64-linux/ghcjs-8.4.0.1/flat-0.4.5/t/spec/build/spec/spec.jsexe/all.js


RUN cd flat;cabal --ghcjs test flat:repr

RUN cd flat;cabal build --enable-tests --ghcjs --constraint "tasty -clock" flat:doc-static

# RUN cd flat;cabal test --ghcjs --constraint "tasty -clock"  flat:repr

# RUN cd flat;cabal --ghcjs --constraint "tasty -clock" test flat:ghcjs-cons


#RUN rm -r flat

ARG CACHE_DATE

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


