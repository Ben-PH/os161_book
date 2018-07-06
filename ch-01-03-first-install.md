# First Install of os161

Want to get os161 working? Let's do it!

This takes three main steps

* Configuring the overall project build.
* Configuring the kernel build.
* Building and installing the kernel.
* Building and installing user-level.

## Configure the project

We want to make sure that our project sits in our system how we want it. This
is done for us by `/src/config`, all we need to do is run the script. Remember 
in [Configure the Setup](ch-01-02-configure-setup.md), how we had a default
project location? That comes into play here.

Theory will go into more depth, but an os is divided into user-space and 
kernel-space, so let's get started on getting each of them setup.

### Kernel

At this point, we are going through the motions, but if you want to dive into the
theory of what the kernel is, TODO: link to kernel theory.

#### configure

Again, our tool of choice is going to be a configure script;  `$(TOP)/src/kern/conf/config`
(instead of) `$(TOP)/src/config` as before. Also, this config needs to be run with a config file
that controlls the script. In this case, we will use `$(TOP)/src/kern/conf/HELLO`
* while in `$(TOP)/src/kern/conf` run `./config HELLO`

#### Build and install

Now that we have the config generated, we can create the binaries, and put them
where they need to be. First, we need to move to the directory where kernel
build is managed
* `cd $(TOP)/src/kern/compile/HELLO/` (or `../compile/HELLO`)
* bmake depend
  * TODO: what does depend do?
* bmake - compiles the binaries
* bmake install - puts files and symbolic links in the right place


### User

We still need to work on the user-level utilities. This one is straight forward:
* `cd $(TOP)/src` && bmake

And there you have it. An operating system ready to go!



