hypeGroups
==========

* Extended search and sort functionality
* API to add new group subtypes
* API to manage group hierarchies
* API for managing group fields
* API for restricting group tools, as well as using preset tools

Group Subtypes
~~~~~~~~~~~~~~

Registering new subtypes and configuring them is made easy.

Here is an example of how to remove groups from the top level of the site, and making them subgroups of a new subtype called classroom.

.. code::

	$svc = \hypeJunction\Groups\GroupsService::instance();

	$svc->registerSubtype('classroom', [
		'labels' => [
			'en' => [
				'item' => 'Classroom',
				'collection' => 'Classrooms',
			],
		],
		'root' => true,
		'identifier' => 'classrooms',
		'class' => \CustomPlugin\Classroom::class,
		'collections' => [
			'all' => \CustomPlugin\DefaultClassroomCollection::class,
			'owner' => \CustomPlugin\OwnedClassroomCollection::class,
			'member' => \CustomPlugin\JoinedClassroomCollection::class,
		],
	]);

	$svc->registerSubtype('group', [
      'site_menu' => false,
		'labels' => [
			'en' => [
				'item' => 'Group',
				'collection' => 'Groups',
			],
		],
		'root' => false,
		'parents' => ['classroom'],
		'identifier' => 'groups',
   ]);


You can put multiple subtypes into a collection by assigning them to the same `identifier`, e.g. you could create `usa_state` and `canada_province` subtypes and register them for `regions` identifier.

Config
~~~~~~

Using `'class'` property of the registered subtype is equivalent to calling `elgg_set_entity_class()`

Collection classes under `'collections'` property auto-wire various collection pages with search and pagination. You can leave them out to default to `hypeGroups` collections, or extend them to implement custom search/filtering logic.

.. code::

   $svc = \hypeJunction\Groups\GroupsService::instance();

   // You can remove core groups
   $svc->unregisterSubtype('group');

   // You can register and configure custom group types
	$svc->registerSubtype('country', [
		'labels' => [
			'en' => [
				'item' => 'Country',
				'collection' => 'Countries',
			],
		],
		'identifier' => 'countries',
		'class' => Country::class, // custom class

      // Allow at root level
		'root' => true,

      // Group subtypes that can be used as parents/containers
      'parents' => [],

      // Restrict available tools
      'tools' => ['blog', 'activity',],

      // Do not allow group admins to change avaialable tools
      'preset_tools' => true,

      // Add link to site menu
      'site_menu' => true,
	]);


Translations
~~~~~~~~~~~~

Newly added group subtypes will generate a ton of untranslated strings. If you are lazy, just run `vendor/bin/elgg-cli groups:translate` and it will generate all the translations for you. You can then copy them into your plugin and update as needed.


Fields
~~~~~~

You can easily add new fields to group schema using hooks found in `hypePost`. Please see the documentation there for more information.