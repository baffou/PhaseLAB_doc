.. dropdown:: **setCalcSjMode** |subTitle| Defines how the Stokes coefficients are calculated. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        objList.setCalcSjMode(val)

        % examples
        objList.setCalcSjMode('Ej') % Sj computed from the complex E fields
        objList.setCalcSjMode('Tj') % Sj computed only from the intensity images



    .. raw:: html
      
        <p class="title">Description</p>

    :matlab:`objList.setCalcSjMode(val)` sets the ``calcSjMode`` property of the objects to the specified value :matlab:`val` that should equal :matlab:`'Ej'` or :matlab:`'Tj'`. If :matlab:`val = 'Ej'`, the Stokes coefficients given by the properties ``S0``, ``S1``, ``S2``, ``S3`` are computed using the complex electric field values given by the properties ``Ex`` and ``Ey``. If :matlab:`val = 'Ej'`, the Stokes coefficients are computed using the intensity images :matlab:`T_j=obj.IM(j).T`. For instance, the computation of ``S2`` can be performed by either of these two expressions:



    .. math::
    
        S_2 &= \frac{T_2+T_4}{2}

        S_2' &= \mathcal{Re}(E_1E_3^*)

    ``S_2'`` comes from ierent measurements since  :math:`E_1` and :math:`E_3` arise from the measurements of :math:`T_1`, :math:`T_3`, :math:`W_1` and :math:`W_3`. The comparison of ``S_2`` and ``S_2'`` is at the basis of the so-called *S2-test*, detailed in Ref. \ [#ACSNanoacceptedbis]_. Both images should be identical, putting apart the noise level. If they differ, it means that the grating-to-camera distance was not set properly when computing the wavefront images using the :ref:`QLSIprocess <The_QLSIprocess_method>` method. It can help determine the proper grating distance. Here is a code example of S2-test.

    .. code-block:: matlab

        obj.setCalcSjMode('Ej')
        S2_E = obj.S2;
        obj.setCalcSjMode('Tj')
        S2_T = obj.S2;

        figure

        % side by side image display:
        subplot(2,2,1),imagegb(S2_E)
        subplot(2,2,2),imagegb(S2_T)
        % crosscuts:
        subplot(2,2,1),imagegb(S2_E(end/2,:))
        subplot(2,2,2),imagegb(S2_T(end/2,:))

    .. [#ACSNanoacceptedbis] *Single-shot polarization imaging of vectorial metasurfaces using cross-grating wavefront microscopy*, J. Flamant, B. Marthy, K. Zangeneh Kamali, N. Ullberg, G. Demesy, P. Ferrand, M. Käll, G. Baffou, **ACS Nano**, accepted (2026)
    
    
    
    |hr|
    