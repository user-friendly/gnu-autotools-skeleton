# ABOUT

A guide for absolute newbies to the GNU auto tools project setup.

# QUICK START

REQUIREMENTS
------------

A GNU/Linux distribution with the GNU autotools setup - autoconf, automake,
libtool and a compatible compiler (GCC, Clang, etc.).

CREATE
------

Change directory to your project's root.
Run `autoscan` (or `autoscan -v`).

You can use the `-v` option for to get more runtime information out of autoscan.

Autoscan will generate the initial configuration file. Think about it as a
"wizzard" program that helps you guide through the first steps of setup.

See https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoscan-Invocation.html

SETUP
-----

Rename `configure.scan` to `configure.ac`.
Edit the `configure.ac`.

This is the part where you have to setup important program configurations.

INSTALL
-------

Run `autoreconf --force --install` (or `autoreconf -fi`).

You can use the `-v` option for to get more runtime information out of
autoreconf. You should get used to executing `autoreconf -vfi` often in the early
setup stages - especially when m4 macros are changed (more on that later).

See https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html_node/autoreconf-Invocation.html
