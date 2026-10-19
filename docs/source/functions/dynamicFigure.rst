.. _The_dynamicFigure_function:

The |c| dynamicFigure |/c| function
-----------------------------------

:py:func:`dynamicFigure` is a function that can display ``Ni`` groups of ``Np`` images successively by pressing left- and right- arrow keys from the keyboard.

Here is a bacic example, 

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', {IM.OPD}, 'bw', {IM.T}, 'titles',{'OPD [nm]','T'})

.. figure:: /images/dynamicFigure.png
   :width: 400
   :align: center

Here, wavefront and intensity images of the |ImageQLSI| object are displayed together with sepia (phase) and b&w color scales. If the ``IM`` is composed of ``Ni`` objects (in this example, :math:`N_i=69`), one can switch from one wavefront-intensity display to the other by pressing the left- and right- arrow keys.




The general prototype is

.. code-block:: matlab
    :linenos:

    dynamicFigure(Name, Value)

The possible Name / Value associations are gathered in the following table:

.. list-table:: Name / Value possibilities for image definition
   :widths: 10 50 50 
   :header-rows: 1
   :align: center

   * - Name
     - Value
     - description
   * - ``bw'``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **black & white** color scale.
   * - ``gb``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **parula** color scale.
   * - ``hot``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **hot** color scale.
   * - ``fl``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with an **inverted green** color scale, typically for fluorescence rendering.
   * - ``hot``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **hot** color scale.
   * - ``ph``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **sepia** color scale, typically for wavefront images.
   * - ``dx``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **3D rendering**, using the :ref:`opendx0 <The_opendx0_function>` function.
   * - ``hsv``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **hsv** color scale.
   * - ``Pr``
     - A matrix, an image object or cell array of matrices
     - displays the image(s) with a **Pradeep** (blue-white-red) color scale.

- There is no limit in the number ``Np`` of Name / Value calls in the function. These calls will give rise to ``Np`` subplots within the displayed figure.
- If the Values are cell arrays, then their dimensions ``Ni`` should be the same thoughout all the Name / Value calls. ``Ni`` will the number of images of each type.



.. list-table:: Name / Value additional features
   :widths: 10 50 50 
   :header-rows: 1
   :align: center

   * - Name
     - Value
     - description
   * - ``titles'``
     - ``Np``-cell array of text
     - list of subplot titles to be displayed.
   * - ``sgtitle``
     - 1-cell or ``Ni``-cell array of text
     - defines a general head title of subplots.
   * - ``pattern``
     - (1,2) double
     - defines the :math:`n\times m` distribution of the subplots.
   * - ``fontsize``
     - double
     - Sets the general font size of the figure
   * - ``range``
     - ``Np``-cell array
     - Sets the clim for each of the ``Np`` image.
   * - ``function``
     - text or function
     - Defines the function to the applied to each image (abs, angle, ...).
   * - ``AxesVisible``
     - logical
     - Displays or not the axes of each subplot.




The most basic example is the following:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IM.OPD)

This code displays the OPD image and the intensity image of the :matlab:`IM` object. The keywords  If :matlab:`IM` is an **array** of |ImageQLSI| objects, then one should add brackets this way:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', {IM.OPD})


it displays the OPD and intensity images of the first object, and one can go from one OPD to the following one by using the left and right arrows. This way, all the OPD images of the :matlab:`IM` array can be easily visualized, without using the heavier GUI using :matlab:`IM.figure`.

.. figure:: /images/displayFigure1.jpg
   :width: 400
   :align: center

One can also display more than one image per figure. For instance, to display both wavefront and intensity, the syntax is:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IMlist,'bw', {IMlist.T})
    linkAxes

.. figure:: /images/displayFigure2.jpg
   :width: 700
   :align: center

The keywork :matlab:`'bw'` just means here display in gray scale. If the braces and the property are omitted, like here where the object ``IMlist`` is simply specified, then the function displays the ``OPD`` by default. The command ``linkAxes`` is optional. It links the two images so that any rescaling of the images using the zoom tool applies to both images.

There is no limit in the number of images that can be displayed. To display the wavefront gradients as well, one can for instance write:

.. code-block:: matlab
    :linenos:

    dynamicFigure('ph', IMlist, 'bw', {IMlist.T}, 'bw', {IMlist.DWx}, 'bw', {IMlist.DWy})
    linkAxes

.. figure:: /images/displayFigure4.png
   :width: 600
   :align: center



To display a figure over the full width of the screen, append the command::

    fullwidth

To display a figure full screen, append the command::

    fullscreen



One can also use this function to display interferograms (main and reference):

.. code-block:: matlab
    :linenos:
    
    dynamicFigure('bw', {Itf.Itf}, 'bw', {Itf.Ref.Itf})
    linkAxes
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
    This function provides a simpler display that the :ref:`figure <The_figure_method>` method and the associated rich GUI. See the :ref:`PhaseLAB GUI <The_PhaseLAB_GUI>` tutorial for details.



