.. include:: /Includes.rst.txt

.. _typo3-fluid-uri-resource:

============
uri.resource
============


A ViewHelper for creating URIs to resources.

Examples
========

Best practice with EXT: syntax
------------------------------

::

   <link href="{f:uri.resource(path:'EXT:indexed_search/Resources/Public/Css/Stylesheet.css')}" rel="stylesheet" />

Output::

   <link href="typo3/sysext/indexed_search/Resources/Public/Css/Stylesheet.css" rel="stylesheet" />

Preferred syntax that works in both extbase and non-extbase context.

Defaults
--------

::

   <link href="{f:uri.resource(path:'Css/Stylesheet.css')}" rel="stylesheet" />

Output::

   <link href="typo3conf/ext/example_extension/Resources/Public/Css/Stylesheet.css" rel="stylesheet" />

Works only in extbase context since it uses the extbase request to find current extension, magically adds 'Resources/Public' to path.

With extension name
-------------------

::

   <link href="{f:uri.resource(path:'Css/Stylesheet.css', extensionName: 'AnotherExtension')}" rel="stylesheet" />

Output::

   <link href="typo3conf/ext/another_extension/Resources/Public/Css/Stylesheet.css" rel="stylesheet" />

Magically adds 'Resources/Public' to path.

Arguments
=========


.. _uri.resource_path:

path
----

:aspect:`DataType`
   string

:aspect:`Required`
   true
:aspect:`Description`
   The path and filename of the resource (relative to Public resource directory of the extension).

.. _uri.resource_extensionname:

extensionName
-------------

:aspect:`DataType`
   string

:aspect:`Required`
   false
:aspect:`Description`
   Target extension name. If not set, the current extension name will be used

.. _uri.resource_absolute:

absolute
--------

:aspect:`DataType`
   mixed

:aspect:`Required`
   false
:aspect:`Description`
   If set, an absolute URI is rendered
