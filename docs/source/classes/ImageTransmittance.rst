.. _The_ImageTransmittance_class:

The ImageTransmittance class
============================

*ImageTransmittance* is a handle class.

An *ImageTransmittance* object represents the image of a 2D material in complex optical transmittance.

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
    * - ``IL``
      - *Illumination*
      - 
      - Illumination
    * - ``sigma_o``
      - (:,:) *double* array
      - 1
      - Ordinary normalized complex eigen-conductivity 
    * - ``sigma_e``
      - (:,:) *double* array
      - 1
      - Extraordinary normalized complex eigen-conductivity 
    * - ``chi_o``
      - (:,:) *double* array
      - 1
      - Ordinary eigen-susceptibility
    * - ``chi_e``
      - (:,:) *double* array
      - 1
      - Extraordinary eigen-susceptibility
    * - ``alpha_o``
      - (:,:) *double* array
      - 1
      - Ordinary complex 2D eigen-polarizability
    * - ``alpha_e``
      - (:,:) *double* array
      - 1
      - Extraordinary complex 2D eigen-polarizability

.. include:: ImageTransmittance/ImageTransmittance_constructor.txt


