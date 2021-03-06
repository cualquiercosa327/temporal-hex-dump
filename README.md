Temporal Hex Dump (THD)
=======================

A tool for visualizing changes to memory over time, as captured by a hardware or software RAM tracer.

This is still in the early stages of development, but this project
is intended to become a graphical analysis tool for memory access
traces. It is designed to handle very large log files efficiently.

Prerequisites
-------------

To compile, requires scons, wxWidgets 2.8, sqlite3, and Boost 1.39 or
later. Only requires wxWidgets and sqlite3 at runtime.

If you're using Debian or Ubuntu, the packages you need are:

  scons
  libsqlite3-dev
  libwxgtk2.8-dev
  wx-common
  libboost-dev

On Mac OS, you can build using the included XCode project. Currently
it assumes you have Boost installed via macports, but it only uses
the header files. It uses the sqlite3 and wxWidgets libraries bundled
with Mac OS 10.5 and later.

UI Hints
--------

- The timeline and grid views both support keyboard navigation.

- Keyboard commands for the timeline view:

     Arrow keys     Select the previous/next transfer
     Page up/down   Go forward/backward by 100 transfers
     +/-            Zoom in/out

- Mouse commands for the timeline view:

     Click          Select the nearest transfer
     Drag           Pan left/right
     Wheel          Zoom in/out
     Shift-wheel    Pan left/right

BUGS
----

- The first transfer and the last one or two transfers are cut off.
  Compare the transfer list in THD with the output of 'decoder' to
  see this.
