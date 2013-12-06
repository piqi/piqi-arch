This repository contains scripts for building an ArchLinux `piqi-git` package
for the *HEAD* version of the `piqi` command-line tool.

The package includes:

1. `/usr/bin/piqi`
2. `PIQI(1)` man page
3. HTML documentation (also available online at
   [http://piqi.org/doc/](http://piqi.org/doc/))


Build prerequisites
-------------------

Install the following packages:

    pacman -S ocaml ocaml-findlib pandoc

    # for running tests
    pacman -S protobuf


Building and installing the package
--------------------

    makepkg
    pacman -U piqi-git*
