# ABOUT

A guide for absolute newbies to the GNU auto tools project setup.

# QUICK START

## REQUIREMENTS

A GNU/Linux distribution with the GNU autotools setup - autoconf, automake,
libtool and a compatible compiler (GCC, Clang, etc.).

## CREATE

* Change directory to your project's root.
* Create `Makefile.am` file.
* Add the following lines:
```
bin_PROGRAMS = example
example_SOURCES = src/main.cpp
```

## SETUP

* Run `autoscan` (or `autoscan -v`).<br />
    You can use the `-v` option for to get more runtime information out of autoscan.<br />
    Autoscan will generate the initial configuration file. Think about it as a
    "wizzard" program that helps you guide through the first steps of setup.<br /><br />
    See [GNU Autoconf: Autoscan Invocation](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoscan-Invocation.html)

* Rename `configure.scan` to `configure.ac`.
* Edit the `configure.ac`.
    * Setup `AC_INIT` arguments.
    * Add `AM_INIT_AUTOMAKE([subdir-objects])` after the `AC_INIT` directive.

## INSTALL

* Run `autoreconf --force --install` (or `autoreconf -fi`).<br />
    You can use the `-v` option for to get more runtime information out of
    autoreconf. You should get used to executing `autoreconf -vfi` often in the early
    setup stages - especially when m4 macros are changed (more on that later).<br /><br />
    See [GNU Autoconf: Autoreconf Invocation](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoreconf-Invocation.html)
* Get an error for missing description files.
    * Create empty files via `touch NEWS README AUTHORS ChangeLog`.
* Repeate previous `autoreconf` command (with the above arguments).

## BUILD

* Create build directory `build` and change to it (`cd build`).
* Run `../configure`.
* Run `make`.

## TEST

* Execute `./src/example`.
