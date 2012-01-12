================================
DjangoCon US website by Eldarion
================================

This repository stores the DjangoCon US website developed by Eldarion. This
project is open source and the license can be found in LICENSE.


Installation
============

To get setup with djangcon code you must have the follow installed:

 * Python 2.6+
 * virtualenv 1.4.7+
 * C compiler (for PIL)

Setting up environment
----------------------

Create a virtual environment where djangocon dependencies will live::

    $ virtualenv --no-site-packages djangocon
    $ source djangocon/bin/activate
    (djangocon)$

Make the project directory your working directory::

    $ cd djangocon_project

Install djangocon project dependencies::

    (djangocon)$ pip install -r requirements/project.txt

Setting up the database
-----------------------

This will vary for production and development. By default the project is set
up to run on a SQLite database. If you are setting up a production database
see the Configuration section below for where to place settings and get the
database running. Now you can run::

    (djangocon)$ python manage.py syncdb

Running a web server
--------------------

In development you should run::

    (djangocon)$ python manage.py runserver

For production, this project comes with a WSGI entry point located in
``deploy/wsgi.py`` and can be referenced by gunicorn with
``deploy.wsgi:application``.

Configuration
=============

You can create a ``local_settings.py`` file alongside ``settings.py`` to
override any setting that may be environment/instance specific. This file is
ignored in ``.gitignore``.

Data configuration
------------------

Create a proposal type (@@@ change once upgraded to newer symposion)::

    >>> from symposion.proposals.models import ProposalKind
    >>> ProposalKind.objects.create(name="Test")

Issues
======

If you find an issue with this code base you are welcome to email us at
development@eldarion.com.
