hypeCaptcha
===========

Protects the site from bots using reCaptcha

Usage
~~~~~

.. code::

   echo elgg_view_field(['#type' => 'captcha']);


Users are only requested to solve a captcha one. If they proved they are human, they won't be bothered again.