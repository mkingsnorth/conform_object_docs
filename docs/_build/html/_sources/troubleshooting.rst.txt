#####################################
Tips and Troubleshooting
#####################################

====================================================================
Bad Deformations
====================================================================


.. figure:: images/bad_deforms.jpg
    :alt: Bad Deformations when mesh topology does not match up.

This can occur for several reasons:

* Not enough topology (vertices, faces) on the source of the target object.
* The tops of the object look best when the effect is not as strong.
* The meshes need more subdivision.

There are several things to try:

* Enable the :ref:`Gradient Effect` to smooth the deformation at the top of the object.
* Increase the resolution of the target object by using a subdivision surface modifier.
* Increase the resolution of the deformation grid in the :ref:`options`.

.. figure:: images/bad_deforms_fixed.jpg
    :alt: Bad Deformations fixed.

    Here, the target sphere object's resolution was increased using a subdivision surface modifier, and the :ref:`Gradient Effect` was enabled for the screw part to lessen the effect at the top.


==================================================================================================================================================
"The bottom of the source object is not pointing towards the target object"
==================================================================================================================================================


.. figure:: images/misalign_error.jpg
    :alt: Misalign error

    This error occurs when the bottom of the source object is not pointing towards the target object.

The bottom of the source object must be pointing towards the target object when running the operation.  The bottom of the object is the lowest part of the object when the object is not rotated.

You will need to orientate the object correctly by rotating it in Object mode:

.. figure:: images/misalign_error_correct.jpg
    :alt: Misalign correction

    The object is rotated correctly as it is pointing towards the target object.

.. figure:: images/misalign_error_correct2.jpg
    :alt: Misalign correction

    The object conformed to the surface.

====================================================================
When Editing the Object, the Effect is Lost
====================================================================

.. figure:: images/edit_error.gif
    :alt: The effect gets lost when editing the object.

    The effect gets lost when editing the object.

    * In :ref:`Grid Mode`, the |Surface Deform Modifier| loses its binding to the surface whenever the underlying mesh is changed.  

        To fix this, select the **Source Object** and the **Target Object** and :ref:`run the conform operation again<How To Use>`.  This will re-apply the modifiers and update the binding.


.. |Surface Deform Modifier| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/modeling/modifiers/deform/surface_deform.html" target="_blank">Surface Deform Modifier</a>


====================================================================
When Copying the Object, the Effect is Lost
====================================================================

.. figure:: images/dupe_error.gif
    :alt: The effect gets lost when duplicating the object.

    The effect gets lost when duplicating the object.

    * In :ref:`Grid Mode`, because the new object would reference the same deformation grid, the effect is automaticaly removed by the add-on to prevent this.  

            To fix this, select the **Source Object** and the **Target Object** and :ref:`run the conform operation again<How To Use>`.  This will re-apply the modifiers and update the binding.

====================================================================
Creating Boolean Cutters
====================================================================


.. figure:: images/boolean_cutter_bad.jpg
    :alt: Example of a bad boolean cutter because Conform operation is not :ref:`applied<Apply>`.

    Example of a bad boolean cutter because Conform operation is not :ref:`applied<Apply>`.


If trying to use the conformed object as a boolean cutter on the target object,  use the :ref:`Apply Conform  Object<Apply>` operation first which will apply all the modifiers - otherwise, Blender will go into a loop where it is trying to use the object to cut, but then the source object itself is trying to deform to the cut shape.

.. figure:: images/boolean_cutter.jpg
    :alt: Remember to Apply the Conform Object operation to the source object before using as a boolean cutter.

    Remember to :ref:`apply<Apply>` the Conform Object operation to the source object before using as a boolean cutter.


====================================================================
When I click off the panel, I lose my settings
====================================================================

This is an unfortunate effect of Blender's one-time operation that the settings are applied just once, and the panel is easily lost.  You can :ref:`re-run the operation<How to Use>` and the modifiers will be replaced, not re-added.  Pressing F9 may bring back the panel, but the settings will not be applied again.


