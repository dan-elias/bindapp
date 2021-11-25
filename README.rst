BindApp
=======

Containerized command-line apps based on jupyter-repo2docker_


Features
--------

* Framework for making apps with no dependencies besides jupyter-repo2docker_ (which is available through dockash_), bash, Docker_
* Self-contained environment for each app
* Code development using Jupyter_

Usage
-----

Each app corresponds to a folder in the `src <./src>`_ folder.

Running an existing app
^^^^^^^^^^^^^^^^^^^^^^^

To run an existing app, first navigate to the directory to be operated on (if
applicable) and then use the `run <./run>`_ script:

.. code-block:: bash

    /path/to/bindapp/run <app name> [args]

Modifying an existing app
^^^^^^^^^^^^^^^^^^^^^^^^^

To modify an app, use the `dev <./dev>`_ script

.. code-block:: bash

    dev <app name>

Making a new app
^^^^^^^^^^^^^^^^

To make a new app:

1. add a folder (named after the app) under `src </.src>`_ containing suitable
   source files for jupyter-repo2docker_
2. If additional arguments are needed to run the app (eg: volumes to be
   mounted), add a script to the `run_args <./run_args>`_ folder which outputs
   those arguments (it can also do any setup required for the use of those
   arguments)


.. _jupyter-repo2docker: https://repo2docker.readthedocs.io/en/latest/
.. _Docker: https://docs.docker.com/
.. _dockash: https://github.com/dan-elias/dockash
.. _Jupyter: https://jupyter.org/
