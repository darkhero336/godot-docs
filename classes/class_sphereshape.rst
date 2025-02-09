.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the SphereShape.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_SphereShape:

SphereShape
===========

**Inherits:** :ref:`Shape<class_Shape>` **<** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Category:** Core

Brief Description
-----------------

Sphere shape for 3D collisions.

Properties
----------

+---------------------------+--------------------------------------------------+-----+
| :ref:`float<class_float>` | :ref:`radius<class_SphereShape_property_radius>` | 1.0 |
+---------------------------+--------------------------------------------------+-----+

Description
-----------

Sphere shape for 3D collisions, which can be set into a :ref:`PhysicsBody<class_PhysicsBody>` or :ref:`Area<class_Area>`. This shape is useful for modeling sphere-like 3D objects.

Property Descriptions
---------------------

.. _class_SphereShape_property_radius:

- :ref:`float<class_float>` **radius**

+-----------+-------------------+
| *Default* | 1.0               |
+-----------+-------------------+
| *Setter*  | set_radius(value) |
+-----------+-------------------+
| *Getter*  | get_radius()      |
+-----------+-------------------+

The sphere's radius. The shape's diameter is double the radius.

