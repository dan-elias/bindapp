BindApp
=======

Containerized command-line apps based on jupyter-repo2docker_


Features
--------

* Framework for making apps with no dependencies besides jupyter-repo2docker_ (which is available through dockash_), bash, Docker_
* Self-contained environment for each app
* Code development using Jupyter_

Installation
------------

Clone the bindapp repo:

.. code-block:: bash

    git clone https://github.com/dan-elias/bindapp.git

Then, copy the bindapp_ script from the bindapp root folder to a location
that is on the bash search PATH.  This script contains a hard-coding of the
location of the root path of the cloned bindapp repo. Edit the file to correct
this as necessary.

Usage
-----

Running an existing app
^^^^^^^^^^^^^^^^^^^^^^^

To run an existing app, first navigate to the directory to be operated on (if
applicable) and then use:

.. code-block:: bash

   bindapp run <app name> [args]

Modifying an existing app
^^^^^^^^^^^^^^^^^^^^^^^^^

To modify an app, use:

.. code-block:: bash

    bindapp dev <app name>

Making a new app
^^^^^^^^^^^^^^^^

To make a new app, first use:

.. code-block:: bash

    bindapp new <app name>

This will make a new subfolder under apps_ to define the app. Navigate to this
folder and then:

* Put suitable jupyter-repo2docker_ environment definition files into the "binder" subfolder

* Add code and jupyter notebooks as necessary within the "project" folder

* If necessary, modify the "run_opts" script to provide additional options to
  be supplied to `docker run`_ when the app is run (eg: for mounting paths or
  config files from the host filesystem)

* Modify the "project/main" script as necessary to act as the app's
  entrypoint.  Note: When the app is run, the host working directory will be
  mounted to project/work

To develop code within the app's environment, use:

.. code-block:: bash

    bindapp dev <app name>


Deleting an app
^^^^^^^^^^^^^^^

To delete an app:

* delete its definition folder located within the bindapp cloned repo at apps_/<app name>
* delete its docker image which has a name of the form: bindapp_<user name>_<app name>


.. _jupyter-repo2docker: https://repo2docker.readthedocs.io/en/latest/
.. _Docker: https://docs.docker.com/
.. _dockash: https://github.com/dan-elias/dockash
.. _Jupyter: https://jupyter.org/
.. _apps: ./apps
.. _bindapp: ./bindapp
