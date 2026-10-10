
.. dropdown:: **acquire_continuous** |subTitle| Acquires a single image. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototype
        buf = obj.acquire_continuous();

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.acquire_continuous()``  launches the acquisition of one image and returns it in a *double* array of size ``[obj.width, obj.height]``.
