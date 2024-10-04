.. dropdown:: **PDCM** |subTitle| Computes the PDCM (phase derivatives closure map) of the OPD image. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>
    

    .. code-block:: matlab

        val = obj.PDCM()

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.PDCM()`` computes the PDCM (phase derivatives closure map) of the ``OPD`` image, as introduced by J. Rizzi et al. [#OE21_17340]_. It is defines as

    .. math::

        \mathrm{PDCM}(x,y) = \frac{\partial \mathrm{DWx}}{\partial y} - \frac{\partial \mathrm{DWy}}{\partial x}


    .. caution:: 
        This function needs to access the :matlab:`IM.DWx` and :matlab:`IM.DWy` properties. When accessing the image gradients by writing :matlab:`IM.DWx` or :matlab:`IM.DWy`, matlab checks whether these matrices exist in the object. They exist if the option :matlab:`saveGradients` was set to :matlab:`true` when creating the object :matlab:`IM` using the :ref:`QLSIprocess <The_QLSIprocess_method>` method (of the class interfero).
        
        .. code-block:: matlab

            IM = Itf.QLSIprocess(IL, 'saveGradients', true)        
        
        If this option was not used, then Matlab computes the gradients from the OPD image, each time the gradients are called. This latter approach is not recommended. If the gradients need to be used for any reason after the |ImageQLSI| objects are created, we recommend using the :matlab:`'saveGradients'` option when calling the QLSIprocess method.






    .. [#OE21_17340] Opt. Express 21, 17340 (2013)






