.. _The_ImageT_class:

The ImageT class
================

*ImageT* is a handle class.
See the :ref:`Temperature computing tutorial <Temperature_Processing>` for more information on how to create and deal with *ImageT* objects.

Properties
----------

.. list-table:: Read-only properties
    :widths: 30 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - default
      - description
    * - ``OPD``
      - *double* array
      - 
      - OPD image
    * - ``TMP``
      - *double* array
      - 
      - Temperature image
    * - ``HSD``
      - *double* array
      - 
      - Heat source density image
    * - ``zT``
      - *double*
      - 0
      - Height at which the temperature was computed



.. list-table:: Dependent properties
    :widths: 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - description
    * - ``Nx``
      - *double*
      - Number of pixels along *x*
    * - ``Ny``
      - double array
      - Number of pixels along *y*


.. include:: ImageT/ImageT_constructor.txt


.. include:: ImageT/ImageT_methods.txt

