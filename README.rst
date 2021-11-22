***********************
cookiecutter-MOAD-pypkg
***********************

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0
.. image:: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
   :target: https://github.com/pre-commit/pre-commit
   :alt: pre-commit

This is a `cookiecutter`_ for Python packages created for UBC EOAS MOAD group projects.

.. _cookiecutter: https://github.com/audreyr/cookiecutter

To create a new package skeleton:

1. Activate the ``cookiecutter`` conda environment::

     $ conda activate cookiecutter

   or create it, then activate it::

     $ conda env create -f cookiecutter-MOAD-pypkg/envs/environment.yaml
     $ conda activate cookiecutter

2. Run this cookie cutter, and answer the prompts, either from a local copy::

     (cookiecutter)$ cookiecutter cookiecutter-MOAD-pypkg/

   or from `its repository`_ on GitHub::

     (cookiecutter)$ cookiecutter gh:UBC-MOAD/cookiecutter-MOAD-pypkg

   .. _its repository: https://github.com/UBC-MOAD/cookiecutter-MOAD-pypkg


License
=======

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0

.. SPDX-License-Identifier: Apache-2.0

This Python package cookiecutter is copyright 2019-2021 by the UBC EOAS MOAD Group
and The University of British Columbia.

It is licensed under the Apache License, Version 2.0.
https://www.apache.org/licenses/LICENSE-2.0.
Please see the LICENSE file for details of the license.
