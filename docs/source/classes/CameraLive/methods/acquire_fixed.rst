
.. dropdown:: **acquire_fixed** |subTitle| Acquires a given number of images in sequence. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototype
        buf = obj.acquire_fixed(Nim);

        % example
        buf = obj.acquire_fixed(30);


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.acquire_fixed(Nim)``  launches the acquisition of ``N`` images on the camera side, and returns them in a 3D *double* array of size ``[obj.width, obj.height, Nim]``.

