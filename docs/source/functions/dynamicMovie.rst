.. _The_dynamicMovie_function:

The |c| dynamicMovie |/c| function
-----------------------------------

:py:func:`dynamicMovie` is a function that transforms of figure created by the :ref:`dynamicFigure function <The_dynamicFigure_function>` into a movie.

For instance:

.. code-block:: matlab
    :linenos:

    h = dynamicFigure("gb",IM,"gb",{IM.DWx},"gb",{IM.DWx},"titles",{"OPD","grad_x OPD","grad_y OPD"});
    fullwidth
    dynamicMovie(h,'movieOPD.avi')


creates a movie from the set of images contained in ``IM``.
