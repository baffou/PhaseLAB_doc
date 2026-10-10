.. _The_ImageEM_class:

The ImageEM class
=================

*ImageEM* is a handle class.

An *ImageEM* represents a 2D distribution (an image) or an electromagnetic wave, characterized by amplitude, phase and polarization components along the x, y, and z directions. *ImageEM* objects are normally generated using simulations, while |ImageQLSI| objects arise from measurements.

Properties
----------



.. list-table:: Read-only properties
    :widths: 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - description
    * - ``Ex``
      - double array
      - :math:`x` component image of the electric field
    * - ``Ey``
      - double array
      - :math:`y` component image of the electric field
    * - ``Ez``
      - double array
      - :math:`z` component image of the electric field
    * - ``Einc``
      - *ImageEM*
      - Incident electric field  
    * - name
      - type
      - description
    * - ``Nx``
      - double
      - Number of columns
    * - ``Ny``
      - double
      - Number of rows
    * - ``E2``
      - double
      - Image of the Efield intensity
    * - ``E``
      - double
      - Amplitude of the Efield
    * - ``Ph``
      - double
      - Phase image

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
      - char
      - 
      - Any comment on the image



.. include:: ImageEM/ImageEM_constructor.txt


.. include:: ImageEM/ImageEM_methods.txt

