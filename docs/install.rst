Installation
============

Using Composer
~~~~~~~~~~~~~~

To use composer, you need to have an active subscription that gives you access to Private Packagist, where hypeJunction plugins are hosted.

.. code::

   ## Add your Private Packagist credentials to global config
   ## You can find your username and token by logging into https://packagist.com/

   composer config --global --auth http-basic.repo.packagist.com <username> <token>


New Project
~~~~~~~~~~~

The easiest way to create an Elgg project with hypeJunction plugins installed is by running the following commands.

.. code::

   ## Create a new Elgg project with hypeJunction Pro plugins pre-installed

   composer create-project hypejunction/hypejunction:dev-master ./project-name

   cd ./project-name

   composer install
   composer install # 2nd call is currently required


Existing Project
~~~~~~~~~~~~~~~~

You can add plugins to an existing project, using

.. code::

   composer install hypejunction/<plugin_name>


Additional Info
~~~~~~~~~~~~~~~

Learn about installation in `Elgg docs`_.

.. _Elgg docs: https://learn.elgg.org/
