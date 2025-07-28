|pypi| |clinicedc|

EDC Detect PII
--------------

check before you push! 

Scan data migrations, notebooks, and other files to look for possible PII exposure.

This is a very simple tool that uses regular expressions. 

Two areas that are at risk of exposing PII are data migrations and jupyter notebooks.

The default regex looks for any word in CAPS greater than two letters and may have spaces between words.

`Clinic EDC <https://github.com/clinicedc>`_ applications handle names, if the project allows, in ALL CAPS.

Usage
=====

.. code-block:: bash

    pip install edc-detect-pii

or if you are using uv 

install the module

.. code-block:: bash

    uv pip install edc-detect-pii

or just run the tool without installing

.. code-block:: bash

    uv run edc_detect_pii.py <OPTIONS>

So far this just looks for names.

To run on migration files, clone the repo and pass a local path. For example:

.. code-block:: bash

    uv run edc_detect_pii.py \
        --repo=/migrations \
        --exclude OTHER ABNORMAL NORMAL \
        --ext=py


To run on a jupyter notebook, pass a local path to a folder with notebooks

.. code-block:: bash

    uv run edc_detect_pii.py \
        --path=/my_notebooks \
        --exclude OTHER ABNORMAL NORMAL



todo
====
* allow custom regex and additional regex as arguments
* consider pre-commit hook that uses a config file of custom words to exclude

.. |pypi| image:: https://img.shields.io/pypi/v/edc-detect-pii.svg
    :target: https://pypi.python.org/pypi/edc-detect-pii

.. |clinicedc| image:: https://img.shields.io/badge/Clinic_EDC-green
   :alt:Made with clinicedc
   :target: https://github.com/clinicedc

