***********************
cookiecutter-moad-pypkg
***********************

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0

This is a `cookiecutter`_ for Python packages created for UBC EOAS MOAD group projects.

.. _cookiecutter: https://github.com/audreyr/cookiecutter

To create a new package skeleton:

1. Activate the ``cookiecutter`` conda environment::

     $ conda activate cookiecutter

   or create it, then activate it::

     $ conda env create -f cookiecutter-moad-pypkg/env/environment.yaml
     $ conda activate cookiecutter

2. Run this cookie cutter, and answer the prompts, either from a local copy::

     (cookiecutter)$ cookiecutter cookiecutter-moad-pypkg/

   or from `its repository`_ on Bitbucket::

     (cookiecutter)$ cookiecutter git+ssh://git@bitbucket.org:douglatornell/cookiecutter-moad-pypkg.git

   .. _its repository: https://bitbucket.org/douglatornell/cookiecutter-moad-pypkg/


License
=======

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0

This Python package cookiecutter is copyright 2019 by the UBC EOAS MOAD Group
and The University of British Columbia.

It is licensed under the Apache License, Version 2.0.
https://www.apache.org/licenses/LICENSE-2.0.
Please see the LICENSE file for details of the license.
