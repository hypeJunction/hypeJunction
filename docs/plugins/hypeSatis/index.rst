hypeSatis
=========

Allows hosting composer repository with private repositories as part of the Elgg site, extending hypeDownloads plugin.

Satis Build
~~~~~~~~~~~

To build Satis composer repository:

.. code::

   vendor/bin/elgg-cli satis:build


You may want to configure a cron job to run this command to pull in new versions of packages at a given interval.

Client Setup
~~~~~~~~~~~~

First, add username and token of the Elgg account to the client server:

.. code::

   composer global config http-basic.{{host}} {{username}} {{token}}


In ``composer.json`` of the client project add:

.. code::

   {
       "repositories": [
           {
               "type": "composer",
               "url": "https://{{host}}/satis"
           }
       ]
   }

Where:

 * ``{{host}}`` is the hostname of your Elgg installation
 * ``{{username}}`` is the username of the Elgg user
 * ``{{token}}`` is the password of the Elgg user

