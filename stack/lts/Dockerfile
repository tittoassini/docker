# Build with: ./mk lts-6.35
FROM quid2/stack
LABEL maintainer="tittoassini@gmail.com"

ARG STK

RUN stack setup --resolver $STK

RUN git clone https://github.com/Quid2/flat
RUN cd flat;stack test --dependencies-only --resolver $STK
RUN rm -rf flat

# RUN git clone https://github.com/Quid2/model
# RUN cd model;stack test --dependencies-only --resolver $STK
# RUN rm -rf model

RUN git clone https://github.com/Quid2/zm
RUN cd zm;stack test --dependencies-only --resolver $STK
RUN cd zm;stack test
RUN rm -rf zm

RUN git clone https://github.com/Quid2/top
RUN cd top;stack build --dependencies-only --resolver $STK
RUN rm -rf top
