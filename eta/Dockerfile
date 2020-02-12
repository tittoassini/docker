FROM typelead/eta
LABEL maintainer="tittoassini@gmail.com"

RUN etlas update

RUN git clone https://github.com/Quid2/flat
RUN cd flat;etlas --enable-tests build
RUN cd flat;etlas test doc
RUN cd flat;etlas test spec
RUN rm -r flat
# ARG CACHEBUST=1
# RUN cd flat;git pull;stack build --resolver $STK


