Installation
============

Using ZIP files
~~~~~~~~~~~~~~~

Distribution (.zip) plugin files can be downloaded from `hypeJunction website`_. To add a plugin, unzip it into your ``/mod`` directory, making sure the directories are not nested, and that ``manifest.xml`` is in the root of the plugin folder.

Using Composer
~~~~~~~~~~~~~~

To use composer, you need to have an active subscription that gives you access to individual packages.

.. code::

   ## Add your satis credentials to global config
   ## You can find your username and token by logging into https://hypejunction.com/ and navigating to one of the downloads.

   composer config --global --auth http-basic.hypejunction.com <username> <token>


Update your ``composer.json`` to include:

.. code::

   "repositories": [
       {
           "type": "composer",
           "url": "https://hypejunction.com/satis"
       }
   ]


New Project
-----------

The easiest way to create an Elgg project with hypeJunction plugins installed is by running the following commands.

.. code::

   ## Create a new Elgg project with hypeJunction Pro plugins pre-installed

   composer create-project hypejunction/hypejunction:dev-master ./project-name

   cd ./project-name

   composer install
   composer install # 2nd call is currently required

   ./elgg-cli install
   ./elgg-cli plugins:activate hypeCli
   ./elgg-cli hypejunction:install


Existing Project
----------------

You can add plugins to an existing project, using

.. code::

   composer require hypejunction/<plugin_name>


Additional Info
~~~~~~~~~~~~~~~

Learn about installation in `Elgg docs`_.

.. _hypeJunction website: https://hypejunction.com/
.. _Elgg docs: https://learn.elgg.org/
