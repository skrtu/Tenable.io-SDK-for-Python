Tenable.io SDK for Python
=========================
.. image:: https://img.shields.io/pypi/v/tenable-io.svg?style=flat-square
    :target: https://pypi.python.org/pypi/tenable-io

Tenable.io SDK for Python

For you coffee lovers, check out `Tenable.io SDK for Java <https://github.com/tenable/Tenable.io-SDK-for-Java>`_.

Installation
------------

.. code-block:: bash

    $ pip install tenable_io

Quick Start
-----------

Quickest way to get started is to checkout the `example scripts <./examples/>`_.

Configuration
-------------

Access key and secret key are needed to authenticate with the
`Tenable Cloud API <https://cloud.tenable.com/api>`_. There are three ways to
supply the keys to the ``TenableIOClient``:

========== ==========
Precedence   Method
========== ==========
   1       Constructor Arguments
   2       INI File
   3       Environment Variables
========== ==========

TenableIOClient Constructor Arguments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: python

    TenableIOClient(access_key='YOUR_ACCESS_KEY', secret_key='YOUR_SECRET_KEY', proxies={ 'http': 'http://proxy:port', 'https': 'https://prxy:port', 'no': '127.0.0.1,192.168.1.0/24' })

INI File
^^^^^^^^

| A ``tenable_io.ini`` can be created in the working directory. See
  ``tenable_io.ini.example`` on what it should look like.
| Note: The ``tenable_io.ini.example`` file is in Jinja template format.

Environment Variables
^^^^^^^^^^^^^^^^^^^^^

TenableIOClient looks for the environment variables ``TENABLEIO_ACCESS_KEY``, ``TENABLEIO_SECRET_KEY`, ``HTTP_PROXY``, ``HTTTPS_PROXY``, and ``NO_PROXY``. If no proxy variable is set via either config or passing it, it will be set to blank for all three.

Python Version
--------------

2.7, 3.4+

Development
-----------

It is recommend to use ``virtualenv`` to setup an isolated local
environment.

.. code:: sh

    $ virtualenv .venv
    # To use a different python bin (i.e. python3).
    $ virtualenv .venv3 -p $(which python3)
    # To active the virtualenv
    $ source ./.venv/bin/activate

Install dependencies.

.. code:: sh

    $ pip install -r ./requirements.txt
    $ pip install -r ./requirements-build.txt

Run Tests
---------

Additional configuration is needed for tests to correctly run. See the
``[tenable_io-test]`` section under ``tenable_io.ini.example``. Such
configuration can be done via the INI file ``tenable_io.ini`` or environment
variables.

.. code:: sh

    $ py.test

Documentations
--------------

To generate/force update the RST documentations from docstrings.

.. code:: sh

    $ sphinx-apidoc -f -o doc/source tenable_io

Generate HTML documentation.

.. code:: sh

    $ cd doc
    $ make clean && make html
