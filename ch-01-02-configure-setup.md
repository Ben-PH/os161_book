# Configure the Setup

An OS is a large and seemingly unweildy piece of kit. Let's fix that.

### Aims
By the end of this chapter, you will:

* Understand how to configure os161 for compilation and installation
* Be primed to learn how to use configuration as a tool.

### Objectives
* Understand what controls the build and install of the OS.
* Have a config file with minor changes tailored to your dev systems.

### Known Issues
* Dependencies missing if using Ubuntu later than v14
* Some automatic processes not yet complete.

```text
This book assumes your project is run in $(HOME)/os161/
The next chapter describes how to change this.
```

### Familiarisation

The two main files of interest are /src/configure and /src/kern/conf/config

#### /src/configure
Looking at this file, we will get a familiarity of the more fundamental
settings for the compiler, and be able to make some changes to suit
our needs. 

* OSTREE. When we build our OS, we need to build the directory tree of
said OS. By default, it is `$(HOME)/os161/root`. I you want this default to be,
`~/Documents/os_proj/`, you will have to change OSTREE accordingly.
* run this script with `./configure`
* note the other variables, at this stage, little more than a curiosity:
  * PLATFORM - related to the toolchain.
  * MACHINE - Would need to change if implimenting for other architecture.
  * DEBUG - will become handy later on, when we start developing.

#### /src/kern/conf/config and ./HELLO
Earlier projects exclusively touch code found below `/src/kern/`. Looking at
these files will allow us to understand how to have some power over this. these
files are best looked at together.

We can see in `./config` that we have recognised directives. `HELLO` alread has
`debug` selected, and a series of devices. If you want to play around with how
the compiler puts things together, this is a great place to start. Note haw we
`include conf/conf.kern`. We will look at that in our first hello-world project.
