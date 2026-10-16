.. _The_imaging_function:

The |c| imaging |/c| function
=============================


.. raw:: html
    
    <p class="title">Syntax</p>

.. code-block:: matlab

    % prototype
    IM = imaging(DIs,MI)
    IM = imaging(DIs,MI,"Npx",N)


.. raw:: html
    
    <p class="title">Description</p>

Function that computes the :math:`E` field at the image plane, corresponding to a given set of dipoles at the sample plane. The computation is based on :abbr:`DDA (discrete dipole approximation)` calculations, which take into account dipoles optical coupling.

|hr|

``DIs`` is an array of |Dipole| objects.

``MI`` is the |Microscope| objects of the setup.

``N`` is the size of the image in pixels (width and height).


.. raw:: html
    
    <p class="title">Example</p>

.. include:: /codeExamples/imageSimulation.rst



