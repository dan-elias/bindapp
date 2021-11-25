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

Each app corresponds to a folder in the src_ folder.

Running an existing app
^^^^^^^^^^^^^^^^^^^^^^^

To run an existing app, first navigate to the directory to be operated on (if
applicable) and then use the run_ script:

.. code-block:: bash

    /path/to/bindapp/run <app name> [args]

Modifying an existing app
^^^^^^^^^^^^^^^^^^^^^^^^^

To modify an app, use the dev_ script

.. code-block:: bash

    dev <app name>

Making a new app
^^^^^^^^^^^^^^^^

To make a new app:

* Under the src_ folder, make a copy of the _template folder with the name of
  the new app.  Within that new folder:

  - Put suitable jupyter-repo2docker_ environment definition files into the
    "binder" subfolder
  - Add code and jupyter notebooks as necessary within the "project" folder
  - Modify the "project/main" script as necessary to act as the app's
    entrypoint.  Note: When the app is run, the host working directory will be
    mounted to project/work

*  If additional arguments are needed to run the app (eg: volumes to be
   mounted), add a script to the `run_args <./run_args>`_ folder which outputs
   those arguments (it can also do any setup required for the use of those
   arguments)


.. _jupyter-repo2docker: https://repo2docker.readthedocs.io/en/latest/
.. _Docker: https://docs.docker.com/
.. _dockash: https://github.com/dan-elias/dockash
.. _Jupyter: https://jupyter.org/
.. _src: ./src
.. _run_args: ./run_args
.. _run: ./run
.. _dev: ./blob/master/dev
