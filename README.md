autotools-unittest
==================

The autotools-unittest is a minimal starter kit when writing C++ library
with autotools, google test(gtest) and google mock(gmock).
This include gtest-1.6.0 and gmock-1.6.0,
so you can use those testing framework without installation.

Requirements
------------

* Autoconf
* Automake
* Libtool

Example
-------

* Change package name from 'autotools-unittest' to your library name(ex. mylib)

<pre><code>
$ ./scripts/change_package_name.sh mylib
Changing package name from 'autotools-unittest' to 'mylib' ... Are you sure? [yes/NO]: yes
===========================================================================
Following directory names will be changed.

* ./test/autotools-unittest
* ./src/autotools-unittest

Are you sure? [yes/NO]: yes

* ./test/autotools-unittest ... done.
* ./src/autotools-unittest ... done.

===========================================================================
Following file contents will be changed.

* ./configure.ac
* ./test/mylib/Makefile.am
* ./test/mylib/sample_test.cpp
* ./test/Makefile.am
* ./src/Makefile.am

Are you sure? [yes/NO]: yes

* ./configure.ac ... done.
* ./test/mylib/Makefile.am ... done.
* ./test/mylib/sample_test.cpp ... done.
* ./test/Makefile.am ... done.
* ./src/Makefile.am ... done.

</code></pre>

Change top directory name yourself.

<pre><code>
$ cd ..
$ mv autotools-unittest mylib
$ cd mylib
</code></pre>

* Build sample codes

<pre><code>
$ ./autogen.sh
$ ./configure
$ make
</code></pre>

* Build gtest, gmock and unit tests for sample codes, and run them

<pre><code>
$ make check
</code></pre>

* Write your library

Tips
----

* Disable gmock

If you don't use gmock, you can avoid unnecessary gmock's build by using --disable-gmock option.

<pre><code>
$ ./configure --disable-gmock
$ make
$ make check
</code></pre>

TODO
----

* Support various tests such as *make check-integration* or *make check-fuzzing*

