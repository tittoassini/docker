# Docker Images

## raspbian-haskell: an Arm7 haskell testing environment

`quid2/raspbian-haskell` is a linux/Arm7 haskell testing environment deployed as a docker image.

It's handy to test haskell code, and in particular low-level code that interacts directly with memory or other platform specific details, in an environment that is quite different from the standard X86 platform.

It should run on any docker host.

It includes:

- Linux kernel 4.4.0-22
- ghc 7.10.3 (with LLVM 3.5.2)
- cabal 1.24.2.0
- stack 1.4.0

You will probably want to run it as an sshd accessible server.

To do so:

- clone this repository:
 
  `git clone https://github.com/tittoassini/docker`

- copy your public key to `docker/raspbian-haskell/root/.ssh/authorized_keys`

- build your ssh accessible server:

  `cd docker/raspbian-haskell;docker build -t raspbian-haskell .`

- run the server:

  `docker run -d -p=2222:22 -t raspbian-haskell`

- connect to the running server:

  `ssh root@<host> -p 2222`
  
To stop the server:

  `docker stop <image-id>`

### Issues 

Compilation times in the simulated Arm7 environment are about 30x slower than when run natively on the X86 host. It is not really an environment you want to develop in, but it's still quite usable for testing.

Large image, about 8G.

### Building the image

To see the steps followed to build the docker image, check the [image docker file](raspbian-haskell/DockerfileImage).

However, trying to build the image using the docker file failed due to an error during the configuration of the ghc compiler, so the image was actually built by entering the commands manually.

### Acknowledgments

Based on info from [reddit](https://www.reddit.com/r/haskell/comments/4h8b5m/deploy_haskell_stack_application_on_raspberry_pi/) and the [resin/rpi-raspbian](https://hub.docker.com/r/resin/rpi-raspbian/) image.
