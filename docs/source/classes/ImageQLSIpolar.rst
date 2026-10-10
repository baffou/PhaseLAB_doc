.. _The_ImageQLSIpolar_class:

The ImageQLSIpolar class
========================

*ImageQLSIpolar* is a handle class.

An *ImageQLSIpolar* object represents a polarization-resolved QLSI measurement. *ImageQLSIpolar* objects arise from measurements using a polarization camera (Flamant et al., ACS Nano (2026)).

Properties
----------

.. list-table:: Read-only properties
    :widths: 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - description
    * - ``IM``
      - (1,4) *ImageQLSI* array
      - Contains the 4 QLSI measurements
    * - ``retardanceMax``
      - *double*
      - Max value of the retardance color scale for figure display
    * - ``eLim``
      - *double*
      - Limit value of the ellipticity color scale for figure display
    * - ``dichroMax``
      - *double*
      - Max value of the dichroism color scale for figure display
    * - ``thetaShift``
      - *double*
      - Artificial shift of the angle of the polarization ellipse


.. list-table:: Dependent properties
    :widths: 30 30 100 
    :header-rows: 1
    :align: center

    * - name
      - type
      - description
    * - ``Nx``
      - *integer*
      - Number of image columns
    * - ``Ny``
      - *integer*
      - Number of image lines
    * - ``Ex``
      - *double* array
      - x-component image of the computed E field
    * - ``Ey``
      - *double* array
      - y-component image of the computed E field
    * - ``S0``
      - *double* array
      - S0 Stokes parameter image
    * - ``S1``
      - *double* array
      - S1 Stokes parameter image
    * - ``S2``
      - *double* array
      - S2 Stokes parameter image
    * - ``S3``
      - *double* array
      - S3 Stokes parameter image
    * - ``A``
      - *double* array
      - Image of the major axis length of the polarization ellipse
    * - ``B``
      - *double* array
      - Image of the minor axis length of the polarization ellipse
    * - ``thetaEllipse``
      - *double* array
      - Orientation angle of the major axis of the polarization ellipse [rad]
    * - ``thetaEllipseDeg``
      - *double* array
      - ... same in degrees
    * - ``h``
      - *double* array
      - Handedness image (1 or -1 values)
    * - ``rgbImageEllipse``
      - (:,:,3) *double* array
      - rgb image, whose color codes the polarization ellipse properties
    * - ``Illumination``
      - *Illumination*
      - Illumination used during image acquisition
    * - ``Microscope``
      - *Microscope*
      - Microscope used to acquire the images


.. include:: ImageQLSIpolar/ImageQLSIpolar_constructor.txt


.. include:: ImageQLSIpolar/ImageQLSIpolar_methods.txt

