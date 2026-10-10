.. _The_MieScattering_function:

The |c| MieScattering |/c| function
-----------------------------------

.. raw:: html
    
    <p class="title">Syntax</p>

.. code-block:: matlab

    % prototype
    props = MieScattering(lambda,radius,n_m,mat)

    % examples
    props = MieScattering(530e-9, 25e-9, 1.33, 'Au')


.. raw:: html
    
    <p class="title">Description</p>

The :py:func:`MieScattering` function computes the optical properties of a sphere using Mie theory. The inputs are the wavelength of the incident light ``lambda``, the radius of the nanoparticle ``radius``, the refractive index of the surrounding medium ``n_m`` and the material ``mat``.

- The material ``mat`` can be a (complex) refractive index, or a material name, such as :matlab:`'Au'`,         :matlab:`'Ag'`, :matlab:`'BK7'`, or any material from the |c| src/spec/material |/c|  folder. To get the list of the possible ``mat`` values, just execute
    .. code-block:: matlab

        Nanoparticle.matList()

- The wavelength ``lambda`` is in [m], and can be an array. In this case, the fields of props are arrays.
- The nanoparticle radius ``radius`` is in [m], and can be an array as well. In this case, the fields of props are arrays. If are both arrays, then the fields size will be a 2-dimensional array of size ``Nlambda x Nradius``.


The function returns a structure ``props`` containing the following fields: ``alpha``, ``Cext``, ``Csca``, ``Cabs``, which are respectively the complex optical polarizability [m^3], the extinction cross section, the scattering cross section and the absorption cross section [m^2]. 

For instance, here is a code that computes the cross sections spectra of a 50-nm gold nanosphere in water:

.. code-block:: matlab
    :linenos:

    lambdaList = (500:20:800)*1e-9;
    radius = 50e-9;
    n_m = 1.33;
    props = MieScattering(lambdaList, radius, n_m,'Au');

    % display
    figure
    hold on
    plot(1e9*lambdaList, props.Cext)
    plot(1e9*lambdaList, props.Cabs)
    plot(1e9*lambdaList, props.Csca)
    legend({'ext','abs','sca'})
    xlabel('wavelength')
    ylabel('cross sections')

.. figure:: /images/MieScattering.png
    :width: 400
    :align: center

