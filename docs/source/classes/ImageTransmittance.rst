.. _The_ImageTransmittance_class:

The ImageTransmittance class
============================

*ImageTransmittance* is a handle class.

An *ImageTransmittance* object represent the image of a 2D material in complex optical transmittance.

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
    * - ``t_o``
      - (:,:) *double* array
      - 1
      - Ordinary eigen-transmittance
    * - ``t_e``
      - (:,:) *double* array
      - 1
      - Extraordinary eigen-transmittance
    * - ``phi``
      - *double* array
      - 0
      - Ordinary axis orientation
    * - ``ME``
      - *Medium*
      - 
      - Surrounding medium structure

.. include:: ImageTransmittance/ImageTransmittance_constructor.txt

.. include:: ImageTransmittance/ImageTransmittance_methods.txt

