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
    * - ``xx``
      - *double* array
      - Intensity image
    * - ``xy``
      - *double* array
      - Intensity image
    * - ``yx``
      - *double* array
      - Intensity image
    * - ``yy``
      - *double* array
      - Intensity image
    * - ``Illumination``
      - *Illumination*
      - Illumination.
    * - ``Microscope``
      - *Microscope*
      - Microscope setup
    * - ``Nx``
      - *Integer*
      - Number of pixel along :math:`(x)`
    * - ``Ny``
      - *Integer*
      - Number of pixel along :math:`(y)`
    * - ``mat``
      - (2,2,:,:) *double*
      - 4-dimensional Jones matrix expression
    * - ``T``
      - *ImageTransmittance**
      - Transmittance image



.. include:: ImageJonesMatrix/ImageJonesMatrix_constructor.txt


.. include:: ImageJonesMatrix/ImageJonesMatrix_methods.txt

