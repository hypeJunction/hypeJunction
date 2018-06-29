hypeAttachments
===============

 * API and UI for attaching files and other entities
 * Form input for uploading file attachments
 * Views for displaying attachments

Register allowed subtypes
~~~~~~~~~~~~~~~~~~~~~~~~~

If you add your entity subtype to a list of entities supporting attachments, the plugin
will attempt to create all of the UI, necessary to upload and display attachments:

.. code::

   elgg_register_plugin_hook_handler('allow_attachments', 'object:my_subtype', '\Elgg\Values::getTrue');


Note that this generic approach might not work with all plugins, and may require additional customizations on your side.

Display an attachment input
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

   echo elgg_view('input/attachments');


To add an attachments input to your comment and discussion replies forms, use the following code. You will not need to add any code to your save action.

.. code::

   echo elgg_view('input/attachments', [
      'name' => 'comment_attachments',
   ]);


To add an attachments input to your personal messages and replies forms, use the following code. You will not need to add any code to your save action.

.. code::

   echo elgg_view('input/attachments', [
      'name' => 'message_attachments',
   ]);


Note that if you are not using *hypeDropzone*, your form must have it's encoding set to ``multipart/form-data``.

Attach uploaded files in an action
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code::

   hypeapps_attach_uploaded_files($entity, 'upload', [
      'access_id' => $entity->access_id, // change the access level of uploaded files
   ]);


Attach an object
~~~~~~~~~~~~~~~~

.. code::

   hypeapps_attach($entity, $attachment);


Display attachments
~~~~~~~~~~~~~~~~~~~

.. code::

   echo elgg_view('output/attachments', [
      'entity' => $entity,
   ]);


Acknowledgements
~~~~~~~~~~~~~~~~

 * Early version of the plugin development has been partially sponsored by [Social Business World](https://socialbusinessworld.org/)
