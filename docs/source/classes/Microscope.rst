.. _The_Microscope_class:

The Microscope class
====================

*Microscope* is a handle class.

A *Microscope* object represents an experimental microscope, containing a camera, an objective lens, a tube lens, a relay-lens, and a cross-grating.

Properties
----------

.. list-table:: Public properties
   :widths: 30 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - default
     - description
   * - ``Objective``
     - *Objective*
     - 
     - Objective lens
   * - ``CGcam``
     - *CGcamera*
     - 
     - QLSI camera
   * - ``f_TL``
     - *double*
     - 180
     - Objective lens
   * - ``software``
     - *char*
     - 
     - software used to acquire the interferograms
   * - ``zo``
     - *double*
     - 0
     - defocus
   * - ``To``
     - *double*
     - 
     - Ambient temperature
   * - ``refl``
     - *logical*
     - false
     - Microscope in reflection mode


.. list-table:: Read-only properties
   :widths: 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - description
   * - ``M``
     - double
     - magnification of the microscope
   * - ``Mobj``
     - double
     - magnification of the objective (can be different from M, depending on the tube lens)
   * - ``NA``
     - double
     - Numerical aperture of the objective
   * - ``pxSize``
     - double
     - pixel size of the image


.. include:: Microscope/Microscope_constructor.txt


.. include:: Microscope/Microscope_methods.txt

