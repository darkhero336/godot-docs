.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the EditorScenePostImport.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorScenePostImport:

EditorScenePostImport
=====================

**Inherits:** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Category:** Core

Brief Description
-----------------

Post-processes scenes after import.

Methods
-------

+-----------------------------+--------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_source_file<class_EditorScenePostImport_method_get_source_file>` **(** **)** const                             |
+-----------------------------+--------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_source_folder<class_EditorScenePostImport_method_get_source_folder>` **(** **)** const                         |
+-----------------------------+--------------------------------------------------------------------------------------------------------------------------+
| :ref:`Object<class_Object>` | :ref:`post_import<class_EditorScenePostImport_method_post_import>` **(** :ref:`Object<class_Object>` scene **)** virtual |
+-----------------------------+--------------------------------------------------------------------------------------------------------------------------+

Description
-----------

Imported scenes can be automatically modified right after import by setting their **Custom Script** Import property to a ``tool`` script that inherits from this class.

The :ref:`post_import<class_EditorScenePostImport_method_post_import>` callback receives the imported scene's root node and returns the modified version of the scene. Usage example:

::

    tool # Needed so it runs in editor
    extends EditorScenePostImport
    
    # This sample changes all node names
    
    # Called right after the scene is imported and gets the root node
    func post_import(scene):
        # Change all node names to "modified_[oldnodename]"
        iterate(scene)
        return scene # Remember to return the imported scene
    
    func iterate(node):
        if node != null:
            node.name = "modified_" + node.name
            for child in node.get_children():
                iterate(child)

Tutorials
---------

- `#custom-script <../getting_started/workflow/assets/importing_scenes.html#custom-script>`_ in :doc:`../getting_started/workflow/assets/importing_scenes`

Method Descriptions
-------------------

.. _class_EditorScenePostImport_method_get_source_file:

- :ref:`String<class_String>` **get_source_file** **(** **)** const

Returns the source file path which got imported (e.g. ``res://scene.dae``).

.. _class_EditorScenePostImport_method_get_source_folder:

- :ref:`String<class_String>` **get_source_folder** **(** **)** const

Returns the resource folder the imported scene file is located in.

.. _class_EditorScenePostImport_method_post_import:

- :ref:`Object<class_Object>` **post_import** **(** :ref:`Object<class_Object>` scene **)** virtual

Called after the scene was imported. This method must return the modified version of the scene.

