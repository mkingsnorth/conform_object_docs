#####################################
Options
#####################################

.. figure:: images/options_panel.jpg
  :alt: Options Panel in the bottom left of the viewport

  Options Panel in the bottom left of the viewport


=====================
Presets
=====================

You can add or remove preset configurations from the tool here by pressing the **+** or **-** keys, or reset the tool to its default parameters.

=======================
Source Object
=======================

The following controls the parameters of how the source object is applied:

Method
--------------------

Choose between :ref:`Grid Mode` or :ref:`ShrinkWrap Mode`.

Gradient Effect
--------------------
This creates a vertex group which automatically weights the vertices at the bottom so the effect is less exagerated at the top:
  
.. figure:: images/conform_obj_2.gif
    :alt: Conform Object at work

    The add-on allows you to control the influence of the deformation.  In this case, we do not want the threads of the screws to be affected, so we reduce the *End* parameter so that the effect finishes towards the bottom of the object.

Gradient Type
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: images/gradient_type.jpg
    :alt: Gradient types

    The type of gradient to apply: *Linear* (Left), or *Constant* (Right)

This is the type of gradient effect to apply:

* **Linear**: this will create a gradually decreasing effect between two values.
* **Constant**: this will create a hard falloff from 1 to 0.

Start/End
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: images/start_end_grad.jpg
    :alt: Start/End controls

    Start/End controls

This controls when the gradient effect of the vertices starts and ends.  

A value of 0.0 is at the bottom of the object, and a value of 1.0 is at the top.  

Lowering the value of the *end* below 1.0 will stop the deformation towards the bottom of the object, and higher values will extend the weight beyond the top of the object.  Increasing the *start* value will start the weighting higher up the object.

.. figure:: images/vertex_group_weighting.jpg
    :alt: Veterx Group Weighting

    The default vertex group weighting, where the effect is gradually reduced towards the top (Start=0.0, End=1.0)

.. figure:: images/vertex_group_weighting_start_pt.jpg
    :alt: Veterx Group Weighting

    Vertex group weighting where the start point has been increased so the effect covers the lower part of the object entirely (Start=0.45, End=0.55)

.. figure:: images/vertex_group_weighting_0.1.jpg
    :alt: Veterx Group Weighting

    A lower vertex group weighting, where the effect is gradually reduced further towards the bottom (Start=0.0, End=0.1)

.. figure:: images/vertex_group_weighting_2.0.jpg
    :alt: Veterx Group Weighting

    A higher vertex group weighting, where the effect is gradually reduced beyond the top of the object (Start=0.0, End=2.0)


.. tip:: Visualise a vertex group in Edit Mode by selecting "Vertex Group Weights" in the |overlays panel|:

    .. image:: images/vertex_group_visualise.jpg
        :alt: Visualising Vertex Groups


.. |overlays panel| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/editors/3dview/display/overlays.html" target="_blank">overlays panel</a>


Blend Normals
------------------------------

This will blend the normals of the source object with the target object, creating a smoother transition between the two object surfaces:

.. figure:: images/gradient_effect_2.jpg
  :alt: Some simple 'horns' applied using the add-on.  They are all separate objects.

  Some simple 'horns' applied using the add-on.  They are all separate objects.

.. figure:: images/gradient_effect_1.jpg
  :alt: Here the normals of the 'horns' are blended with the normals of the head.

  Here the normals of the same 'horn' objects are blended with the normals of the head.  They remain separate objects.


This effect is achieved by using a |Data Transfer Modifier| on the Source Object.

.. |Data Transfer Modifier| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/modeling/modifiers/modify/data_transfer.html" target="_blank">Data Transfer Modifier</a>

Start/End (Blend Normals)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: images/start_end_blend.jpg
    :alt: Start/End controls

    Start/End controls for normal blending

As with the :ref:`Start/End` controls for the :ref:`Gradient Effect`, this controls which face normals are affected.

Blend Whole Object
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This will blend all of the object's normals regardless of the gradient effect.


Add Simple Subdivisions
------------------------------

This adds a |Subdivision Surface modifier| to the source object, set to 'simple', in case you wish to quickly subdivide the mesh when conforming the object.

* **Subdivisions**: The number of subdivisions to use in the modifier.

.. |Subdivision Surface modifier| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/subdivision_surface.html" target="_blank">Subdivision Surface modifier</a>

Align Object to Face
------------------------------

This will automatically align the source object to the face of the target object it is being applied to if it is not already.


Collapse Modifiers
------------------------------

This will collapse the existing modifiers on the source object if they are interfering with the conform effect.

Deform Modifier Position
------------------------------

This will change the position of the deformation modifier (Either :ref:`Surface Deformation<Grid Mode>` of :ref:`ShrinkWrap<ShrinkWrap Mode>`) on the source object:

* **Start**: At the start of the modifier stack.
* **Before**: This will place the modifier just before a specified modifier.  Selecting the option will allow you to specify which modifier.

    .. image:: images/mod_before.jpg
        :alt: Placing a modifier before another.

* **End**: At the start of the modifier stack.

=======================
Grid Object
=======================

This controls the nature of the deformation grid used in :ref:`Grid Mode`.  It is a regular blender object, parented to the source object, but is configurable by the add-on:


Hide Grid
------------------------------

By default, the deformation grid is hidden but it can be displayed if you wish to configure it:

.. figure:: images/hide_grid.gif
  :alt: The deformation grid is revealed!

  The deformation grid is revealed!


Grid Subdivisions
------------------------------

.. figure:: images/grid_subd.gif
  :alt: Subdividing the grid increases the resolution of the deformation.

  Subdividing the grid increases the resolution of the deformation.

The number of vertices in the grid.  If you are deforming over particularly smoothed or high resolution meshes, increasing this number can be useful.


Grid X/Y
-------------

.. figure:: images/move_grid_x.jpg
  :alt: Grid moved in X direction.

  Grid moved in X direction.

Move the grid's X/Y position.


Grid Scale X/Y
--------------------------

.. figure:: images/grid_scale.gif
  :alt: Scale the influence of the grid.

  Scale the influence of the grid.

Scale the grid in the X/Y direction.


Grid Rotation
--------------------------

.. figure:: images/grid_rotation.gif
  :alt: Grid rotated on surface.

  Grid rotated on surface.

Rotate the grid over the surface.



Interpolation Falloff
--------------------------

Used on the |Surface Deform Modifier| for the grid. From the |documentation|: 

*"How much a vertex bound to one face of the target will be affected by the surrounding faces (this setting is unavailable after binding). This essentially controls how smooth the deformations are."*


.. |Surface Deform Modifier| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/modeling/modifiers/deform/surface_deform.html" target="_blank">Surface Deform Modifier</a>


.. |documentation| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/modeling/modifiers/deform/surface_deform.html" target="_blank">documentation</a>