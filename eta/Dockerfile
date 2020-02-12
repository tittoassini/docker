FROM typelead/eta
LABEL maintainer="tittoassini@gmail.com"

RUN etlas update

RUN git clone https://github.com/Quid2/flat;cd flat;etlas build --enable-tests

RUN rm -rf flat

# ARG CACHEBUST=1
# docker run -it typelead/eta git clone https://github.com/Quid2/flat;cd flat;etlas update;etlas test

