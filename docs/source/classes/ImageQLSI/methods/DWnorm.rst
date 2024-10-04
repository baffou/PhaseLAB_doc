.. dropdown:: **DWnorm** |subTitle| Returns the norm of the gradient of the OPD image of the *ImageQLSI* object. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>
    
    .. code-block:: python

        val = obj.DWnorm()

    Returns the norm of the gradient image, computed from the two gradient images :matlab:`DWx` and :matlab:`DWy`. 


    .. caution:: 
        When accessing the image gradients by writing :matlab:`IM.DWx` or :matlab:`IM.DWy`, matlab checks whether these matrices exist in the object. They exist if the option :matlab:`saveGradients` was set to :matlab:`true` when creating the object :matlab:`IM` using the :ref:`QLSIprocess <The_QLSIprocess_method>` method (of the class interfero).
        
        .. code-block:: matlab

            IM = Itf.QLSIprocess(IL, 'saveGradients', true)        
        
        If this option was not used, then Matlab computes the gradients from the OPD image, each time the gradients are called. This latter approach is not recommended. If the gradients need to be used for any reason after the |ImageQLSI| objects are created, we recommend using the :matlab:`'saveGradients'` option when calling the QLSIprocess method.






