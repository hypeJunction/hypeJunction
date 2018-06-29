hypeModerator
=============

Implements moderator role

Approval Workflow
~~~~~~~~~~~~~~~~~

Approval workflow only works with entities that use ``publish`` event.

To queue entities for approval use a hook handler:

.. code::

   elgg_register_plugin_hook_handler('uses:moderation', 'object:<entity_subtype>`, '\Elgg\Values::getTrue`);
