hypeShortcode
=============

Add support for custom BB-style shortcodes

Register shortcode
~~~~~~~~~~~~~~~~~~

.. code::

   elgg()->shortcodes->register('mycode');

   // then add a view in shortcodes/mycode
   // view vars will contain attributes of the shortcode


Generate a shortcode tag
~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

   elgg()->shortcodes->generate('mycode', [
      'foo' => 'bar',
   ]);


Expand shortcodes
~~~~~~~~~~~~~~~~~

.. code::

   elgg()->shortcodes->expand($text);


Strip shortcodes
~~~~~~~~~~~~~~~~

.. code::

   elgg()->shortcodes->strip($text);

