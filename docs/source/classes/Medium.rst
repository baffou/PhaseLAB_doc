.. _The_Medium_class:

The Medium class
======================

*Medium* is a handle class.

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
   * - ``n0``
     - *double* or *char*
     - 
     - refractive index or nature of the upper medium
   * - ``nS0``
     - *double* or *char*
     - 
     - refractive index or nature of the upper medium
   * - ``Illumination``
     - *Illumination*
     - 
     - Illumination of the microscope



.. list-table:: Dependent properties
   :widths: 30 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - dependence
     - description
   * - ``n``
     - *double*
     -
     - refractive index of the upper medium
   * - ``nS``
     - *double*
     -
     - refractive index of the lower medium
   * - ``lambda``
     - *double*
     - ``= obj.Illumination.lambda;;``
     - incident electric field


.. include:: Medium/Medium_constructor.txt

.. include:: Medium/Medium_methods.txt

