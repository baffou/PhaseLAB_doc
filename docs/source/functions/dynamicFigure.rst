.. _The_dynamicFigure_function:

The |c| dynamicFigure |/c| function
-----------------------------------

:py:func:`dynamicFigure` is a function that can display more than one type of image in one figure (wavefront and intensity for instance). It also enables the navigation thoughout a series of images using the left- and right-arrow keys of the keyboard.

For instance:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IM)

displays the OPD image of the :matlab:`IM` object. If :matlab:`IM` is an **array** of |ImageQLSI| objects, then it displays the OPD of the first object, and one can go from one OPD to the following one by using the left and right arrows. This way, all the OPD images of the :matlab:`IM` array can be easily visualized.

.. figure:: /images/displayFigure1.jpg
   :width: 400
   :align: center

One can also display more than one image per figure. For instance, to display both wavefront and intensity, the synthax is:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IMlist,'bw', {IMlist.T})
    linkAxes

Don't forget the braces when calling the property of the object. The keywork :matlab:`'bw'` just means here display in gray scale. The command ``linkAxes`` is optional. It links the two images so that any rescaling of the images using the zoom tool applies to both images.

.. figure:: /images/displayFigure2.jpg
   :width: 700
   :align: center

There is no limit in the number of images that can be displayed. On can for instance write:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IMlist,'bw', {IMlist.T},'bw', {IMlist.DWx},'bw', {IMlist.DWy})
    linkAxes

.. figure:: /images/displayFigure4.png
   :width: 600
   :align: center


to display the wavefront gradients as well.

To display a figure full screen, append the command::

    fullscreen

To display a figure over the full screen width, append the command::

    fullwidth


One can also use this function to display interferograms (main and reference):

.. code-block:: matlab
    :linenos:
    
    dynamicFigure('bw', {Itf.Itf}, 'bw', {Itf.Ref.Itf})
    fullscreen

One can add the :matlab:`"titles"` keyword to enter titles to be displayed on top of each image:

.. code-block:: matlab
    :linenos:
    
    dynamicFigure('gb',IM,'gb',{IM.DWx},'gb',{IM.DWy}, ...
         "titles",{'OPD','DWx','DWy'})
    linkAxes


.. figure:: /images/displayFigureTitles.png
   :width: 800
   :align: center


.. note::
    Importantly, this function also works if ``IM`` or ``Itf`` is an object *array*. In this case, the first object of the series is primarily displayed, and then, by pressing the right-arrow or left-arrow keys, one can navigate to the next or previous images.



