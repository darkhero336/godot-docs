.. Generated automatically by doc/tools/makerst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the MultiMesh.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_MultiMesh:

MultiMesh
=========

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

**Category:** Core

Brief Description
-----------------

Provides high-performance mesh instancing.

Properties
----------

+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`ColorFormat<enum_MultiMesh_ColorFormat>`           | :ref:`color_format<class_MultiMesh_property_color_format>`                     | 0  |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`CustomDataFormat<enum_MultiMesh_CustomDataFormat>` | :ref:`custom_data_format<class_MultiMesh_property_custom_data_format>`         | 0  |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`int<class_int>`                                    | :ref:`instance_count<class_MultiMesh_property_instance_count>`                 | 0  |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`Mesh<class_Mesh>`                                  | :ref:`mesh<class_MultiMesh_property_mesh>`                                     |    |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`TransformFormat<enum_MultiMesh_TransformFormat>`   | :ref:`transform_format<class_MultiMesh_property_transform_format>`             | 0  |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+
| :ref:`int<class_int>`                                    | :ref:`visible_instance_count<class_MultiMesh_property_visible_instance_count>` | -1 |
+----------------------------------------------------------+--------------------------------------------------------------------------------+----+

Methods
-------

+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`AABB<class_AABB>`               | :ref:`get_aabb<class_MultiMesh_method_get_aabb>` **(** **)** const                                                                                                             |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Color<class_Color>`             | :ref:`get_instance_color<class_MultiMesh_method_get_instance_color>` **(** :ref:`int<class_int>` instance **)** const                                                          |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Color<class_Color>`             | :ref:`get_instance_custom_data<class_MultiMesh_method_get_instance_custom_data>` **(** :ref:`int<class_int>` instance **)** const                                              |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform<class_Transform>`     | :ref:`get_instance_transform<class_MultiMesh_method_get_instance_transform>` **(** :ref:`int<class_int>` instance **)** const                                                  |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Transform2D<class_Transform2D>` | :ref:`get_instance_transform_2d<class_MultiMesh_method_get_instance_transform_2d>` **(** :ref:`int<class_int>` instance **)** const                                            |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_as_bulk_array<class_MultiMesh_method_set_as_bulk_array>` **(** :ref:`PoolRealArray<class_PoolRealArray>` array **)**                                                 |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_instance_color<class_MultiMesh_method_set_instance_color>` **(** :ref:`int<class_int>` instance, :ref:`Color<class_Color>` color **)**                               |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_instance_custom_data<class_MultiMesh_method_set_instance_custom_data>` **(** :ref:`int<class_int>` instance, :ref:`Color<class_Color>` custom_data **)**             |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_instance_transform<class_MultiMesh_method_set_instance_transform>` **(** :ref:`int<class_int>` instance, :ref:`Transform<class_Transform>` transform **)**           |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                  | :ref:`set_instance_transform_2d<class_MultiMesh_method_set_instance_transform_2d>` **(** :ref:`int<class_int>` instance, :ref:`Transform2D<class_Transform2D>` transform **)** |
+---------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Enumerations
------------

.. _enum_MultiMesh_TransformFormat:

.. _class_MultiMesh_constant_TRANSFORM_2D:

.. _class_MultiMesh_constant_TRANSFORM_3D:

enum **TransformFormat**:

- **TRANSFORM_2D** = **0** --- Use this when using 2D transforms.

- **TRANSFORM_3D** = **1** --- Use this when using 3D transforms.

.. _enum_MultiMesh_ColorFormat:

.. _class_MultiMesh_constant_COLOR_NONE:

.. _class_MultiMesh_constant_COLOR_8BIT:

.. _class_MultiMesh_constant_COLOR_FLOAT:

enum **ColorFormat**:

- **COLOR_NONE** = **0** --- Use when you are not using per-instance :ref:`Color<class_Color>`\ s.

- **COLOR_8BIT** = **1** --- Compress :ref:`Color<class_Color>` data into 8 bits when passing to shader. This uses less memory and can be faster, but the :ref:`Color<class_Color>` loses precision.

- **COLOR_FLOAT** = **2** --- The :ref:`Color<class_Color>` passed into :ref:`set_instance_color<class_MultiMesh_method_set_instance_color>` will use 4 floats. Use this for highest precision :ref:`Color<class_Color>`.

.. _enum_MultiMesh_CustomDataFormat:

.. _class_MultiMesh_constant_CUSTOM_DATA_NONE:

.. _class_MultiMesh_constant_CUSTOM_DATA_8BIT:

.. _class_MultiMesh_constant_CUSTOM_DATA_FLOAT:

enum **CustomDataFormat**:

- **CUSTOM_DATA_NONE** = **0** --- Use when you are not using per-instance custom data.

- **CUSTOM_DATA_8BIT** = **1** --- Compress custom_data into 8 bits when passing to shader. This uses less memory and can be faster, but loses precision.

- **CUSTOM_DATA_FLOAT** = **2** --- The :ref:`Color<class_Color>` passed into :ref:`set_instance_custom_data<class_MultiMesh_method_set_instance_custom_data>` will use 4 floats. Use this for highest precision.

Description
-----------

MultiMesh provides low-level mesh instancing. Drawing thousands of :ref:`MeshInstance<class_MeshInstance>` nodes can be slow, since each object is submitted to the GPU then drawn individually.

MultiMesh is much faster as it can draw thousands of instances with a single draw call, resulting in less API overhead.

As a drawback, if the instances are too far away of each other, performance may be reduced as every single instance will always rendered (they are spatially indexed as one, for the whole object).

Since instances may have any behavior, the AABB used for visibility must be provided by the user.

Tutorials
---------

- :doc:`../tutorials/3d/vertex_animation/animating_thousands_of_fish`

Property Descriptions
---------------------

.. _class_MultiMesh_property_color_format:

- :ref:`ColorFormat<enum_MultiMesh_ColorFormat>` **color_format**

+-----------+-------------------------+
| *Default* | 0                       |
+-----------+-------------------------+
| *Setter*  | set_color_format(value) |
+-----------+-------------------------+
| *Getter*  | get_color_format()      |
+-----------+-------------------------+

Format of colors in color array that gets passed to shader.

.. _class_MultiMesh_property_custom_data_format:

- :ref:`CustomDataFormat<enum_MultiMesh_CustomDataFormat>` **custom_data_format**

+-----------+-------------------------------+
| *Default* | 0                             |
+-----------+-------------------------------+
| *Setter*  | set_custom_data_format(value) |
+-----------+-------------------------------+
| *Getter*  | get_custom_data_format()      |
+-----------+-------------------------------+

Format of custom data in custom data array that gets passed to shader.

.. _class_MultiMesh_property_instance_count:

- :ref:`int<class_int>` **instance_count**

+-----------+---------------------------+
| *Default* | 0                         |
+-----------+---------------------------+
| *Setter*  | set_instance_count(value) |
+-----------+---------------------------+
| *Getter*  | get_instance_count()      |
+-----------+---------------------------+

Number of instances that will get drawn. This clears and (re)sizes the buffers. By default, all instances are drawn but you can limit this with :ref:`visible_instance_count<class_MultiMesh_property_visible_instance_count>`.

.. _class_MultiMesh_property_mesh:

- :ref:`Mesh<class_Mesh>` **mesh**

+----------+-----------------+
| *Setter* | set_mesh(value) |
+----------+-----------------+
| *Getter* | get_mesh()      |
+----------+-----------------+

Mesh to be drawn.

.. _class_MultiMesh_property_transform_format:

- :ref:`TransformFormat<enum_MultiMesh_TransformFormat>` **transform_format**

+-----------+-----------------------------+
| *Default* | 0                           |
+-----------+-----------------------------+
| *Setter*  | set_transform_format(value) |
+-----------+-----------------------------+
| *Getter*  | get_transform_format()      |
+-----------+-----------------------------+

Format of transform used to transform mesh, either 2D or 3D.

.. _class_MultiMesh_property_visible_instance_count:

- :ref:`int<class_int>` **visible_instance_count**

+-----------+-----------------------------------+
| *Default* | -1                                |
+-----------+-----------------------------------+
| *Setter*  | set_visible_instance_count(value) |
+-----------+-----------------------------------+
| *Getter*  | get_visible_instance_count()      |
+-----------+-----------------------------------+

Limits the number of instances drawn, -1 draws all instances. Changing this does not change the sizes of the buffers.

Method Descriptions
-------------------

.. _class_MultiMesh_method_get_aabb:

- :ref:`AABB<class_AABB>` **get_aabb** **(** **)** const

Returns the visibility axis-aligned bounding box.

.. _class_MultiMesh_method_get_instance_color:

- :ref:`Color<class_Color>` **get_instance_color** **(** :ref:`int<class_int>` instance **)** const

Gets a specific instance's color.

.. _class_MultiMesh_method_get_instance_custom_data:

- :ref:`Color<class_Color>` **get_instance_custom_data** **(** :ref:`int<class_int>` instance **)** const

Returns the custom data that has been set for a specific instance.

.. _class_MultiMesh_method_get_instance_transform:

- :ref:`Transform<class_Transform>` **get_instance_transform** **(** :ref:`int<class_int>` instance **)** const

Returns the :ref:`Transform<class_Transform>` of a specific instance.

.. _class_MultiMesh_method_get_instance_transform_2d:

- :ref:`Transform2D<class_Transform2D>` **get_instance_transform_2d** **(** :ref:`int<class_int>` instance **)** const

Returns the :ref:`Transform2D<class_Transform2D>` of a specific instance.

.. _class_MultiMesh_method_set_as_bulk_array:

- void **set_as_bulk_array** **(** :ref:`PoolRealArray<class_PoolRealArray>` array **)**

Sets all data related to the instances in one go. This is especially useful when loading the data from disk or preparing the data from GDNative.

All data is packed in one large float array. An array may look like this: Transform for instance 1, color data for instance 1, custom data for instance 1, transform for instance 2, color data for instance 2, etc...

:ref:`Transform<class_Transform>` is stored as 12 floats, :ref:`Transform2D<class_Transform2D>` is stored as 8 floats, ``COLOR_8BIT`` / ``CUSTOM_DATA_8BIT`` is stored as 1 float (4 bytes as is) and ``COLOR_FLOAT`` / ``CUSTOM_DATA_FLOAT`` is stored as 4 floats.

.. _class_MultiMesh_method_set_instance_color:

- void **set_instance_color** **(** :ref:`int<class_int>` instance, :ref:`Color<class_Color>` color **)**

Sets the color of a specific instance.

For the color to take effect, ensure that :ref:`color_format<class_MultiMesh_property_color_format>` is non-``null`` on the ``MultiMesh`` and :ref:`SpatialMaterial.vertex_color_use_as_albedo<class_SpatialMaterial_property_vertex_color_use_as_albedo>` is ``true`` on the material.

.. _class_MultiMesh_method_set_instance_custom_data:

- void **set_instance_custom_data** **(** :ref:`int<class_int>` instance, :ref:`Color<class_Color>` custom_data **)**

Sets custom data for a specific instance. Although :ref:`Color<class_Color>` is used, it is just a container for 4 numbers.

.. _class_MultiMesh_method_set_instance_transform:

- void **set_instance_transform** **(** :ref:`int<class_int>` instance, :ref:`Transform<class_Transform>` transform **)**

Sets the :ref:`Transform<class_Transform>` for a specific instance.

.. _class_MultiMesh_method_set_instance_transform_2d:

- void **set_instance_transform_2d** **(** :ref:`int<class_int>` instance, :ref:`Transform2D<class_Transform2D>` transform **)**

Sets the :ref:`Transform2D<class_Transform2D>` for a specific instance.

