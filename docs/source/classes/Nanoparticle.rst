.. _The_Nanoparticle_class:

The Nanoparticle class
======================

*Nanoparticle* is a variable class (not a handle class!).

It represents a meshed nanoparticle in the object space of the microscope, to be used for numerical simulations of optical properties and microscope image.

.. warning::

    Unlike *handle* classes, with a *variable* class, the methods do not modify the object itself. For instance, :matlab:`obj.moveTo('x',1e-6)` does not affect ``obj``. One should write :matlab:`obj = obj.moveTo('x',1e-6);` or  :matlab:`obj2 = obj.moveTo('x',1e-6);`. Also, :matlab:`obj2 = obj;` creates a new, independent object.


Properties
----------

.. list-table:: Read-only  properties
    :widths: 30 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - default
      - description
    * - ``DIs``
      - *Dipole* array
      - 
      - List of the dipoles constituting the nanoparticle
    * - ``geom``
      - *char*
      - 
      - Name of the geometry  
    * - ``params``
      - *double* array
      - 
      - Parameters of the geomtry
    * - ``a``
      - *double*
      - 
      - lattice parameter
    * - ``V``
      - *double*
      - 
      - Volume of the nanoparticle
    * - ``pos``
      - *double* array
      - 
      - Position list of the meshing unit elements
    * - ``mat``
      - *char*
      - 
      - Material of the nanoparticle
    * - ``N``
      - *integer*
      - 
      - Number of dipoles
    * - ``n``
      - *complex*
      - 
      - complex refractive index of the NP material







.. include:: Nanoparticle/Nanoparticle_constructor.txt


.. include:: Nanoparticle/Nanoparticle_methods.txt

