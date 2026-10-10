.. _The_Illumination_class:

The Illumination class
======================

*Illumination* is a handle class.

An *Illumination* object represents the illumination system of the experimental setup.

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
   * - ``lambda``
     - *double*
     - 
     - illumination wavelength \[m\]
   * - ``I``
     - *double*
     - 1
     - Illumination irradiance (power per unit area)
   * - ``direct``
     - (1,3) *double*
     - [0 0 1]
     - unit vector defining the direction of propagation
   * - ``polar``
     - (1,3) *char*
     - [1 0 0]
     - polarization unit vector
   * - ``NA``
     - *double*
     - 0
     - Numerical aperture of the illumination



.. list-table:: Read-only properties
   :widths: 30 30 30 100 
   :header-rows: 1
   :align: center

   * - name
     - type
     - dependence
     - description
   * - ``n``
     - double
     - ``= Medium.n``
     - refractive index of the upper medium
   * - ``nS``
     - double
     - ``= Medium.nS``
     - refractive index of the lower medium
   * - ``e0``
     - double
     - ``= sqrt(2*I/(n*c*eps0));``
     - incident electric field
   * - ``k0``
     - double
     - ``= 2*pi./lambda;``
     - wavevector in vacuum  \[m\ :sup:`-1`\ \]
   * - ``tr``
     - double
     - ``= 2*n/(n+nS);``
     - light transmission at the interface
   * - ``S0``
     - double
     - ``= abs(polar(1)).^2 + abs(polar(2)).^2;``
     - S0 Stokes coefficient
   * - ``S1``
     - double
     - ``= abs(polar(1)).^2 - abs(polar(2)).^2;``
     - S1 Stokes coefficient
   * - ``S2``
     - double
     - ``= 2*real(polar(1).*polar(2)');``
     - S2 Stokes coefficient
   * - ``S3``
     - double
     - ``= 2*imag(polar(1)*polar(2)');``
     - S3 Stokes coefficient


.. include:: Illumination/Illumination_constructor.txt

.. include:: Illumination/Illumination_methods.txt

