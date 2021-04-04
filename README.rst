Mypy plugin for PYLS
======================

.. image:: https://badge.fury.io/py/mypy-ls.svg
    :target: https://badge.fury.io/py/mypy-ls

.. image:: https://github.com/Richardk2n/pyls-mypy/workflows/Python%20package/badge.svg?branch=master
    :target: https://github.com/Richardk2n/pyls-mypy/

This is a plugin for the Palantir's Python Language Server (https://github.com/palantir/python-language-server)

It, like mypy, requires Python 3.6 or newer.


Installation
------------

Install into the same virtualenv as pyls itself.

``pip install mypy-ls``

Configuration
-------------

``prepend`` (default is ``[]``) list of additional command-line options to prepend
``live_mode`` (default is True) provides type checking as you type. This writes to a tempfile every time a check is done.

Turning off live_mode means you must save your changes for mypy diagnostics to update correctly.

Depending on your editor, the configuration (found in a file called mypy-ls.cfg in your workspace or a parent directory) should be roughly like this:

::

    {
	"enabled": True,
	"live_mode": True,
	"strict": False
	"prepend": ["--python-executable", "/tmp/foo/bin/python"]
    }

``dmypy`` (default is False) executes via `dmypy run` rather than `mypy`.

This uses the `dmypy` daemon and may dramatically improve the responsiveness of the `pyls` server.

Depending on your editor, the configuration (found in a file called mypy-ls.cfg in your workspace or a parent directory) should be roughly like this:

::

    {
	"enabled": True,
	"live_mode": False,
	"dmypy": True,
	"strict": False,
	"prepend": ["--python-executable", "/tmp/foo/bin/python"]
    }
