

# mini-tcl [![Build Status](https://travis-ci.org/twilley/mini-tcl.svg?branch=master)](https://travis-ci.org/twilley/mini-tcl) [![](https://images.microbadger.com/badges/image/twilley/mini-tcl.svg)](http://microbadger.com/images/twilley/mini-tcl)
An Alpine Linux based mini Tcl for Docker.

This contains a restricted set of packages necessary for running Tcl 8.6
applications. It is based on an installation of the packages available in Alpine
Linux, and an install of the latest tcllib. That should leave you with tls,
expect, all the Tcl 8.6 packages (threads, database connections, etc.) and the
whole of the tcllib.  The [pure-tcl readline](http://wiki.tcl.tk/20215) is
enabled by default for the root user in the container so you will have a decent
prompt at the command line.

The busybox (3.3 through 3.6) or the busybox-extras (3.7+) package is also installed.

## Building and Running

To build, simply write:

    docker build -t twilley/mini-tcl .

To run and get an interactive Tcl prompt:

    docker run -it --rm twilley/mini-tcl

## Running your own scripts

This image exports `/opt/tcl` as a volume and arranges to give that
directory and its sub-directory `lib` as additional locations when
looking for packages.  This means that you should be able to mount
local directories onto `/opt/tcl` to run your own code within the
container.

Additionally, the image exports `/opt/data` to place random data that
you might wish to access from within the container.

## Versions and Tags

This image tries to follow the release cycle of the
[official](https://hub.docker.com/_/alpine/) Alpine linux image from docker.
Available are the following tags:

* [edge](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-edge)
* [latest](https://github.com/twilley/mini-tcl/blob/master/Dockerfile)
* [3.7](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-3.7)
* [3.6](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-3.6)
* [3.5](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-3.5)
* [3.4](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-3.4)
* [3.3](https://github.com/twilley/mini-tcl/blob/master/Dockerfile-3.3)

## Credits

Forked from https://github.com/efrecon/mini-tcl/

Thanks to the maintainer of the [Tcl package on
Alpine](http://pkgs.alpinelinux.org/package/main/x86_64/tcl) to have spent the
time providing the initial [tls
package](http://pkgs.alpinelinux.org/package/testing/x86_64/tls).
