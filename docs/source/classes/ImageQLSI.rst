.. _The_ImageQLSI_class:

The ImageQLSI class
===================

*ImageQLSI* is a handle class.

An *ImageQLSI* object represents a QLSI measurement, containing, among many other things, intensity and wavefront images. *ImageQLSI* objects arise from measurements, while |ImageEM| objects are normally generated using simulations.

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


.. include:: ImageQLSI/ImageQLSI_constructor.txt


.. include:: ImageQLSI/ImageQLSI_methods.txt

