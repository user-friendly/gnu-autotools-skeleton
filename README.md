# ABOUT

A guide for absolute newbies to the GNU auto tools project setup.

# QUICK START

## REQUIREMENTS

A GNU/Linux distribution with the GNU autotools setup - autoconf, automake,
libtool and a compatible compiler (GCC, Clang, etc.).

## CREATE

* Change directory to your project's root.
* Create `Makefile.am` file.
* Add the line `SUBDIR = src` to it - this is where your sources are located.
* Crate `src/Makefile.am` file.
* Add the following lines.

    bin_PROGRAMS = example
    example_SOURCES = main.cpp

## SETUP

* Run `autoscan` (or `autoscan -v`).<br />
    You can use the `-v` option for to get more runtime information out of autoscan.<br />
    Autoscan will generate the initial configuration file. Think about it as a
    "wizzard" program that helps you guide through the first steps of setup.<br /><br />
    See [GNU Autoconf: Autoscan Invocation](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoscan-Invocation.html)

* Rename `configure.scan` to `configure.ac`.
* Edit the `configure.ac`.
    * Setup `AC_INIT` arguments.
    * Add `AM_INIT_AUTOMAKE` after the `AC_INIT` (and `AC_CONFIG_*`) directive(s).

## INSTALL

Run `autoreconf --force --install` (or `autoreconf -fi`).

You can use the `-v` option for to get more runtime information out of
autoreconf. You should get used to executing `autoreconf -vfi` often in the early
setup stages - especially when m4 macros are changed (more on that later).

See [GNU Autoconf: Autoreconf Invocation](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoreconf-Invocation.html)
