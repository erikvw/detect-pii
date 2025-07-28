EDC Detect PII
--------------

So far this just looks for names.

The default regex looks for any word in CAPS greater than two letters and may have spaces between words. You can pass your own regex.

To run on migration files, clone the repo and pass a local path. For example:

.. code-block:: bash

    uv run detect_pii.py \
        --repo=/migrations \
        --exclude OTHER ABNORMAL NORMAL \
        --ext=py


To run on a jupyter notebook, pass a local path to a folder with notebooks

.. code-block:: bash

    uv run detect_pii.py \
        --path=/my_notebooks \
        --exclude OTHER ABNORMAL NORMAL



todo
----
 - allow custon regex and additional regex
