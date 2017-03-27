# Raspbian (arm7) plus haskell
# Includes:
# - ghc 7.10.3
# - cabal 1.24.2.0
#   ??and ?stack,
# - sshd accessible via my key 

# based on info from: https://www.reddit.com/r/haskell/comments/4h8b5m/deploy_haskell_stack_application_on_raspberry_pi/

# HOW TO:

# build:
# docker build -t quid2:raspbian-haskell .

# run:
# docker run --name raspbian-haskell -d -p=2222:22  -t quid2:raspbian-haskell

# stop:
# docker stop <id>

# commit:
# docker commit <id> quid2:raspbian-haskell

# connect:
# ssh root@<host> -p 2222

FROM      resin/rpi-raspbian
MAINTAINER Titto Assini <tittoassini@gmail.com>

# make sure the package repository is up to date
RUN apt-get update;apt-get -y upgrade

# install necessary system libs
RUN apt-get install -y apt-utils openssh-server openssh-blacklist openssh-blacklist-extra xz-utils wget curl git less screen
RUN apt-get install -y libedit2 libglu1-mesa-dev libgmp3-dev zlib1g-dev libtool

# install stack does not work
# RUN curl -sSL https://get.haskellstack.org/ | sh

# so we install ghc/llvm

# get llvm-3.5.2, as the one in the repository doesn't seem to work either
RUN wget http://llvm.org/releases/3.5.2/clang+llvm-3.5.2-armv7a-linux-gnueabihf.tar.xz
RUN tar xf clang*
RUN cd clang* && cp -R * /usr/local/

# and ghc
RUN wget -q http://downloads.haskell.org/~ghc/7.10.3/ghc-7.10.3-armv7-deb8-linux.tar.xz
RUN tar -xf ghc-7.10.3-armv7-deb8-linux.tar.xz 
RUN ls ghc-7.10.3
RUN pwd

# BAD: qemu: uncaught target signal 11 (Segmentation fault) - core dumped
# configure: error: cannot determine current directory
RUN cd ghc-7.10.3 && ./configure && make install

# and then bootstrap cabal (as the one in the repository is too old)
# this is going to take for ever
RUN wget http://hackage.haskell.org/package/cabal-install-1.24.0.2/cabal-install-1.24.0.2.tar.gz
RUN tar xz cabal-install*
RUN cd cabal-install* && EXTRA_CONFIGURE_OPTS="" ./bootstrap.sh

RUN export PATH=$HOME/.cabal/bin:$PATH
RUN cabal update

# now we can install stack too, this will take forever too
RUN cabal install stack 

# and now sshd
# sshd
EXPOSE 22

# sshd dir
RUN mkdir -p /var/run/sshd

# copy all files
ADD . .

# Make VM accessible with my SSH key
RUN ["chown","-R","root:root","/root"]

CMD /DockerStart
