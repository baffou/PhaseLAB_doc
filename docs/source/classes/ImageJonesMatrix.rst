.. _The_ImageJonesMatrix_class:

The ImageJonesMatrix class
==========================

*ImageJonesMatrix* is a handle class.

An *ImageJonesMatrix* object represents a Jones matrix, which contains by definition all the optical properties of a 2D material.

Properties
----------

.. list-table:: Read-only properties
    :widths: 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - description
    * - ``T``
      - *double* array
      - Intensity image
    * - ``OPD``
      - *double* array
      - OPD image
    * - ``OPDnm``
      - *double* array
      - OPD image in nanometers
    * - ``DWx``
      - *double* array
      - OPD gradient along *x*
    * - ``DWy``
      - *double* array
      - OPD gradient along *y*
    * - ``Ph``
      - *double* array
      - Phase image
    * - ``Nx``
      - *double*
      - Number of columns
    * - ``Ny``
      - *double*
      - Number of rows
    * - ``ItfFileName``
      - *char*
      - Name of the interferogram file from which the object originates.
    * - ``channel``
      - *char*
      - Channel type. ``None`` by default. Can be ``'R','G','0','45','90','135','none'``.



.. list-table:: Public properties
    :widths: 30 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - default
      - description
    * - ``Microscope``
      - *Microscope*
      - 
      - Microscope object
    * - ``Illumination``
      - *Illumination*
      - 
      - Illumination object
    * - ``comment``
      - *char*
      - 
      - Any comment on the image


.. include:: ImageJonesMatrix/ImageJonesMatrix_constructor.txt


.. include:: ImageJonesMatrix/ImageJonesMatrix_methods.txt

