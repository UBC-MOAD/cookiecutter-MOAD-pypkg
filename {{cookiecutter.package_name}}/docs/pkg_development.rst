.. Copyright {{ cookiecutter.project_creation_year }}, {{ cookiecutter.copyright_holder }}
..
.. Licensed under the Apache License, Version 2.0 (the "License");
.. you may not use this file except in compliance with the License.
.. You may obtain a copy of the License at
..
..    https://www.apache.org/licenses/LICENSE-2.0
..
.. Unless required by applicable law or agreed to in writing, software
.. distributed under the License is distributed on an "AS IS" BASIS,
.. WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
.. See the License for the specific language governing permissions and
.. limitations under the License.


.. _{{ cookiecutter.package_name }}PackagedDevelopment:

**********************************************************
:kbd:`{{ cookiecutter.package_slug }}` Package Development
**********************************************************


.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0
.. image:: https://img.shields.io/badge/python-{{ cookiecutter.min_python_version }}+-blue.svg
    :target: https://docs.python.org/{{ cookiecutter.dev_python_version }}/
    :alt: Python Version
.. image:: https://img.shields.io/badge/version%20control-hg-blue.svg
    :target: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/
    :alt: Mercurial on Bitbucket
.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://black.readthedocs.io/en/stable/
    :alt: The uncompromising Python code formatter
.. image:: https://readthedocs.org/projects/{{ cookiecutter.package_name.lower() }}/badge/?version=latest
    :target: https://{{ cookiecutter.package_name.lower() }}.readthedocs.io/en/latest/
    :alt: Documentation Status
.. image:: https://img.shields.io/bitbucket/issues/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}.svg
    :target: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/issues?status=new&status=open
    :alt: Issue Tracker

The {{ cookiecutter.package_name }} package (:kbd:`{{ cookiecutter.package_slug }}`) is {{ cookiecutter.project_short_description }}


.. _{{ cookiecutter.package_name }}PythonVersions:

Python Versions
===============

.. image:: https://img.shields.io/badge/python-{{ cookiecutter.min_python_version }}+-blue.svg
    :target: https://docs.python.org/{{ cookiecutter.dev_python_version }}/
    :alt: Python Version

The :kbd:`{{ cookiecutter.package_slug }}` package is developed and tested using `Python`_ {{ cookiecutter.dev_python_version }} or later.
The package uses some Python language features that are not available in versions prior to 3.6,
in particular:

* `formatted string literals`_
  (aka *f-strings*)
* the `file system path protocol`_

.. _Python: https://www.python.org/
.. _formatted string literals: https://docs.python.org/3/reference/lexical_analysis.html#f-strings
.. _file system path protocol: https://docs.python.org/3/whatsnew/3.6.html#whatsnew36-pep519


.. _{{ cookiecutter.package_name }}GettingTheCode:

Getting the Code
================

.. image:: https://img.shields.io/badge/version%20control-hg-blue.svg
    :target: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/
    :alt: Mercurial on Bitbucket

Clone the code and documentation `repository`_ from Bitbucket with:

.. _repository: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/

.. code-block:: bash

    $ hg clone ssh://hg@bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }} {{ cookiecutter.package_name }}

or

.. code-block:: bash

    $ hg clone https://your_userid@bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }} {{ cookiecutter.package_name }}

if you don't have `ssh key authentication`_ set up on Bitbucket
(or copy the link from the :guilabel:`Clone or download` button on the `repository`_ page).

.. _ssh key authentication: https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html


.. _{{ cookiecutter.package_name }}DevelopmentEnvironment:

Development Environment
=======================

Setting up an isolated development environment using `Conda`_ is recommended.
Assuming that you have the `Anaconda Python Distribution`_ or `Miniconda3`_ installed,
you can create and activate an environment called :kbd:`{{ cookiecutter.package_name.lower() }}` that will have all of the Python packages necessary for development,
testing,
and building the documentation with the commands below.

.. _Conda: https://conda.io/en/latest/
.. _Anaconda Python Distribution: https://www.anaconda.com/distribution/
.. _Miniconda3: https://docs.conda.io/en/latest/miniconda.html

.. code-block:: bash

    $ cd {{ cookiecutter.package_name }}
    $ conda env create -f env/environment-dev.yaml
    $ source activate {{ cookiecutter.package_name.lower() }}
    ({{ cookiecutter.conda_dev_env_name }})$ pip install --editable .

The :kbd:`--editable` option in the :command:`pip install` command above installs the package from the cloned repo via symlinks so that the installed package will be automatically updated as the repo evolves.

To deactivate the environment use:

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ source deactivate


.. _{{ cookiecutter.package_name }}CodingStyle:

Coding Style
============

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://black.readthedocs.io/en/stable/
    :alt: The uncompromising Python code formatter

The :kbd:`{{ cookiecutter.package_name }}` package uses the `black`_ code formatting tool to maintain a coding style that is very close to `PEP 8`_.

.. _black: https://black.readthedocs.io/en/stable/
.. _PEP 8: https://www.python.org/dev/peps/pep-0008/

:command:`black` is installed as part of the :ref:`{{ cookiecutter.package_name }}DevelopmentEnvironment` setup.

To run :command:`black` on the entire code-base use:

.. code-block:: bash

    $ cd {{ cookiecutter.package_name }}
    $ conda activate {{ cookiecutter.package_slug }}
    ({{ cookiecutter.conda_dev_env_name }})$ black ./

in the repository root directory.
The output looks something like::

  **add example black output**


.. _{{ cookiecutter.package_name }}BuildingTheDocumentation:

Building the Documentation
==========================

.. image:: https://readthedocs.org/projects/{{ cookiecutter.package_name.lower() }}/badge/?version=latest
    :target: https://{{ cookiecutter.package_name.lower() }}.readthedocs.io/en/latest/
    :alt: Documentation Status

The documentation for the :kbd:`{{ cookiecutter.package_name }}` package is written in `reStructuredText`_ and converted to HTML using `Sphinx`_.
Creating a :ref:`{{ cookiecutter.package_name }}DevelopmentEnvironment` as described above includes the installation of Sphinx.
Building the documentation is driven by the :file:`docs/Makefile`.
With your :kbd:`salishsea-nowcast` development environment activated,
use:

.. _reStructuredText: http://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html
.. _Sphinx: http://www.sphinx-doc.org/en/master/

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ (cd docs && make clean html)

to do a clean build of the documentation.
The output looks something like::

  **add example Sphinx output**

The HTML rendering of the docs ends up in :file:`docs/_build/html/`.
You can open the :file:`index.html` file in that directory tree in your browser to preview the results of the build.

If you have write access to the `repository`_ on Bitbucket,
whenever you push changes to Bitbucket the documentation is automatically re-built and rendered at https://{{ cookiecutter.package_name.lower() }}.readthedocs.io/en/latest/.


.. _{{ cookiecutter.package_name }}LinkCheckingTheDocumentation:

Link Checking the Documentation
-------------------------------

Sphinx also provides a link checker utility which can be run to find broken or redirected links in the docs.
With your :kbd:`{{ cookiecutter.package_name.lower() }})` environment activated,
use:

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }}))$ cd {{ cookiecutter.package_name }})/docs/
    ({{ cookiecutter.conda_dev_env_name }})) docs$ make linkcheck

The output looks something like::

  **add example linkcheck output**

Look for any errors in the above output or in _build/linkcheck/output.txt


.. _{{ cookiecutter.package_name }}RunningTheUnitTests:

Running the Unit Tests
======================

The test suite for the :kbd:`{{ cookiecutter.package_name }}` package is in :file:`{{ cookiecutter.package_name }}/tests/`.
The `pytest`_ tool is used for test parametrization and as the test runner for the suite.

.. _pytest: https://docs.pytest.org/en/latest/

With your :kbd:`{{ cookiecutter.package_name.lower() }}` development environment activated,
use:

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ cd {{ cookiecutter.package_name }}/
    ({{ cookiecutter.conda_dev_env_name }})$ py.test

to run the test suite.
The output looks something like::

  **add example pytest output**

You can monitor what lines of code the test suite exercises using the `coverage.py`_ tool with the command:

.. _coverage.py: https://coverage.readthedocs.io/en/latest/

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ cd {{ cookiecutter.package_name }}/
    ({{ cookiecutter.conda_dev_env_name }})$ coverage run -m py.test

and generate a test coverage report with:

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ coverage report

to produce a plain text report,
or

.. code-block:: bash

    ({{ cookiecutter.conda_dev_env_name }})$ coverage html

to produce an HTML report that you can view in your browser by opening :file:`{{ cookiecutter.package_name }}/htmlcov/index.html`.


.. _{{ cookiecutter.package_name }}VersionControlRepository:

Version Control Repository
==========================

.. image:: https://img.shields.io/badge/version%20control-hg-blue.svg
    :target: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/
    :alt: Mercurial on Bitbucket

The :kbd:`{{ cookiecutter.package_name }}` package code and documentation source files are available as a `Mercurial`_ repository at https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/.

.. _Mercurial: https://www.mercurial-scm.org/


.. _{{ cookiecutter.package_name }}IssueTracker:

Issue Tracker
=============

.. image:: https://img.shields.io/bitbucket/issues/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}.svg
    :target: https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/issues?status=new&status=open
    :alt: Issue Tracker

Development tasks,
bug reports,
and enhancement ideas are recorded and managed in the issue tracker at https://bitbucket.org/{{ cookiecutter.bbitbucket_team }}/{{ cookiecutter.bitbucket_repo_name }}/issues.


License
=======

.. image:: https://img.shields.io/badge/license-Apache%202-cb2533.svg
    :target: https://www.apache.org/licenses/LICENSE-2.0
    :alt: Licensed under the Apache License, Version 2.0

The code and documentation of the {{ cookiecutter.project_name }} project
are copyright {{ cookiecutter.project_creation_year }} by {{ cookiecutter.copyright_holder }}.

They are licensed under the Apache License, Version 2.0.
https://www.apache.org/licenses/LICENSE-2.0
Please see the LICENSE file for details of the license.
