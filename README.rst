win_unc
=======

Python library for handling UNC mounting on Windows. - |TravisBadge|_

.. |TravisBadge| image:: https://secure.travis-ci.org/CovenantEyes/py_win_unc.png?branch=master
.. _TravisBadge: http://travis-ci.org/CovenantEyes/py_win_unc


Installation
------------

To install::

    $ pip install win_unc


Basic Usage
===========

Below is a simple example::

    from win_unc import UncDirectoryMount, UncDirectory, DiskDrive

    conn = UncDirectoryMount(UncDirectory(r'\\home\shared'), DiskDrive('Z:'))
    conn.connect()
    print 'Drive connected:', conn.is_connected()
    conn.disconnect()

You can also provide credentials like this::

    from win_unc import UncCredentials

    unc = UncDirectory(r'\\home\shared', UncCredentials('user', 'pwd'))
    conn = UncDirectoryMount(unc, DiskDrive('Z:'))


Unit Testing
============

To run the unit tests, do the following::

    $ python test/run_tests.py

For all the tests to run, you must perform them on a Windows machine::

    > python test\run_tests.py


License
=======

This package is released under the
`MIT License`_. (See LICENSE.txt.)

.. _MIT License: http://www.opensource.org/licenses/mit-license.php