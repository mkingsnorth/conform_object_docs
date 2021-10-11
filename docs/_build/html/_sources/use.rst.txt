#####################################
How To Use
#####################################

===========================
Main Use
===========================

.. figure:: images/conform_object_how_to.gif
  :alt: How to use Conform Object


To conform a  **Source Object** to a **Target Object**:

#. Select the **Source Object**.  Source objects need to have the following:

    * When they have no rotation, the 'bottom' of the object is pointing to the bottom of the world view:

        .. figure:: images/conform_source_object.jpg
            :alt: Source Object

    * Ideally source objects also:
        * Have a good level of topology so that they can be deformed (good number of vertices and quad faces)
        * Do not have modifiers such as booleans which are dependent on other objects.
        * Do not have lots of parents/children.

#. Position the object on top of the surface of the **target object** you wish to wrap it to, where the 'bottom' of the object is pointing towards the faces you wish to place it on:

    .. figure:: images/source_object_positioning.jpg
        :alt: Source Object

        Here, the **source object** has been rotated 90 degrees and is pointing towards the **target object**'s forehead.

    You can also position the object on the surface using the **Toggle Surface Snapping** option.

#. Select both the **source object** and then the **target object**:

    .. figure:: images/selected.jpg
        :alt: Both objects selected.

        Both objects selected, with the target object being the active object (the last object selected)

    #. The **source object**, hold shift, and then select
    #. The **target object**

    So that both objects are selected.

#. Right-click in the viewport, and select the **Conform Object** menu.  Select **Conform Object**:

    .. figure:: images/conform_object_menu.jpg
        :alt: Conform Object Menu Option.

#. The object will now be conformed to the target object. In the bottom right of the viewport, you can expand the menu to view :ref:`options`:

    .. figure:: images/object_conformed.jpg
        :alt: The object, conformed.

        The object, conformed.

======================================================
Multiple Objects
======================================================

.. figure:: images/conform_multiple.gif
    :alt: Conforming multiple objects at once.

    Conforming multiple objects at once.

It is also possilbe to conform multiple objects at once using the same operation:

#. Shift-click select the objects you want to conform, and then select the target object last (making it the active object).
#. Right-click and select the **Conform Object** sub menu.
#. Select the **Conform Object** option as usual.

You can then edit the :ref:`Options` of all the objects at the same time.

