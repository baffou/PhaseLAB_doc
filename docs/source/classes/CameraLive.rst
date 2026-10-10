.. _The_CameraLive_class:

The CameraLive class
====================

*CameraLive* is a handle class, abstract class, subclass of *Camera*.

A *CameraLive* object represents the basis experimental camera.

Properties of the Camera class
------------------------------

.. list-table:: Private properties
  :widths: 30 30 30 100 
  :header-rows: 1
  :align: center

  * - name
    - type
    - default
    - description
  * - ``dxSize``
    - *double*
    - 6.5e-6
    - dexel size :math:`p` \[m\]
  * - ``Nx``
    - *integer*
    - 600
    - number of columns :math:`N_x`
  * - ``Ny``
    - *integer*
    - 600
    - number of columns :math:`N_y`
  * - ``fullWellCapacity``
    - *integer*
    - 25000
    - Full-well-capacity :math:`w`
  * - ``brand``
    - *char*
    - 
    - Brand of the camera
  * - ``model``
    - *char*
    - 
    - Model of the camera
  * - ``offset``
    - *double*
    - 0
    - Offset in the dark image
  * - ``bitDepth``
    - *double*
    - 
    - Maximum bit depth (12-bit, 16-bit, ...)
  * - ``colorChannels``
    - *Integer*, 1, 2 or 3
    - 1
    - Number of color channels
  * - ``crosstalk12``
    - *double*
    - 0
    - Crosstalk from dexel 1 to 2
  * - ``crosstalk21``
    - *double*
    - 0
    - Crosstalk from dexel 2 to 1


Specific properties of the CameraLive class
-------------------------------------------

.. list-table:: Private properties
  :widths: 30 30 30 100 
  :header-rows: 1
  :align: center

  * - name
    - type
    - default
    - description
  * - ``hndl``
    - handle
    - 
    - Camera handle to the connected experimental camera
  * - ``status``
    - *double*
    - 
    - Status of the camera (Live, Stop, Burst, etc)
  * - ``expTime``
    - *double*
    - 
    - Exposure time
  * - ``imagesize``
    - *double*
    - 
    - Image size in bytes
  * - ``width``
    - *double*
    - 
    - crop dimension, must be less than or equal to Nx
  * - ``height``
    - *double*
    - 
    - crop dimension, must be less than or equal to Ny
  * - ``top``
    - *double*
    - 
    - position of the bottom-left corner in y
  * - ``left``
    - *double*
    - 
    - position of the bottom-left corner in x
  * - ``stride``
    - *double*
    - 
    - 

.. include:: CameraLive/CameraLive_constructor.txt


.. include:: CameraLive/CameraLive_methods.txt

