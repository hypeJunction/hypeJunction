hypeDropzone
============

Drag&Drop File Uploads for Elgg

* Cross-browser support for drag&drop file uploads
* Easy to integrate into existing forms
* Supports chunked uploads of large files

Adding a drag&drop file input and processing uploads
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To add a drag&drop input to your form, add the following:

.. code::

   echo elgg_view('input/dropzone', array(
         'name' => 'upload_guids',
         'accept' => "image/*",
         'max' => 25,
         'multiple' => true,
         'container_guid' => $container_guid, // optional file container
         'subtype' => $subtype, // subtype of the file entities to be created
         // see the view for more options
   ));


In your action, you can retrieve uploaded files with ```get_input('upload_guids');```

You also need to implement a fallback solution for when the browser does not support
drag and drop. Check ``hypeJunction\DropzoneService`` for an example.


Initializing and resetting dropzone
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can instantiate and clear dropzone by triggering jQuery events on the containing form:

.. code::

   $('.elgg-form').trigger('initialize'); // will instantiate dropzone inputs contained within the form
   $('.elgg-form').trigger('reset'); // will clear previews and hidden guid inputs


Acknowledgements
~~~~~~~~~~~~~~~~

* Dropzone.js is a really cool library by Matias Meno
http://www.dropzonejs.com/
