# Build with: ./mk lts-6.35

# ubuntu + stack
#FROM quid2/stack

# huge images with everyting
FROM fpco/stack-build:$STK

LABEL maintainer="tittoassini@gmail.com"

ARG STK

RUN stack setup --resolver $STK

RUN git clone https://github.com/Quid2/flat
RUN cd flat;stack build --dependencies-only  --resolver $STK
RUN cd flat;stack build --resolver $STK
RUN cd flat;stack test --resolver $STK
#ARG CACHEBUST=5
#RUN cd flat;git pull;stack build --resolver $STK
RUN rm -rf zm

# RUN git clone https://github.com/Quid2/model
# RUN cd model;stack test --dependencies-only --resolver $STK
# RUN rm -rf model

# RUN git clone https://github.com/Quid2/zm
# RUN cd zm;stack test --dependencies-only --resolver $STK
# RUN cd zm;stack build --resolver $STK
# RUN cd zm;stack test --resolver $STK
# RUN rm -rf zm

# Won't yet work with ghc 8.8.X (failing dependenciy acid-state)
# RUN git clone https://github.com/Quid2/top
# RUN cd top;stack build --dependencies-only --resolver $STK
# RUN rm -rf top
