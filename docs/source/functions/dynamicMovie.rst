.. _The_dynamicMovie_function:

The |c| dynamicMovie |/c| function
-----------------------------------

:py:func:`dynamicMovie` is a function that transforms a figure created by the :ref:`dynamicFigure function <The_dynamicFigure_function>` into a movie.

For instance:

.. code-block:: matlab
    :linenos:

    % Generation of the dynamic figure
    h = dynamicFigure("gb",IM,"gb",{IM.DWx},"gb",{IM.DWx},...
        "titles",{"OPD","grad_x OPD","grad_y OPD"});
 
    % Generation of the movie
    dynamicMovie(h,'movieOPD.avi')


creates a movie from the set of images contained in ``IM``.

By default, the frame rate is 1.5 Hz, it can be changed by modifying either the frame rate or the time between two successive images, using a Name-value pattern:

.. code-block:: matlab
    :linenos:

    dynamicMovie(h,'movieOPD.avi', 'rate', 25)
    % or
    dynamicMovie(h,'movieOPD.avi', 'period', 0.02)

