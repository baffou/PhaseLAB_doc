.. _The_MediumT_class:

The MediumT class
======================

*MediumT* is a handle class.

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
   * - ``h``
     - *double*
     - 
     - Thickness of the layer medium.
   * - ``num``
     - *double*
     - 
     - Number of the layer: 1(substrate), 2(medium), 3(cover)


.. list-table:: (GetAccess=public , SetAccess=private)
   :widths: 30 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - default
     - description
   * - ``name``
     - ``'water'``, ``'glycerol'``, ``'BK7'`` or ``'none'``
     - 
     - Material of the medium ( can be 'water', 'glycerol', 'BK7' or 'none').
   * - ``mesh``
     - *double* or *char*
     - 
     - refractive index or nature of the upper medium
   * - ``mesh_param``
     - *Mesh*
     - 
     - Coordinates of the points meshing the layer in z.
   * - ``mesh_Npx``
     - *double* 
     - 
     - Number of mesh points


.. list-table:: Dependent properties
   :widths: 30 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - dependence
     - description
   * - ``kappa``
     - *double*
     -
     - Thermal conductivity of the medium.
   * - ``b``
     - *double*
     - 
     - 4-number vector defining the dn/dT fit coefficients b1, b2, b3, b4.


.. include:: MediumT/MediumT_constructor.txt

