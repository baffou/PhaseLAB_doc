
.. dropdown:: **setCameraROI** |subTitle| Sets the dimensions of the active area of the camera sensor. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototypes
        obj.setCameraROI(size)
        obj.setCameraROI(Nx,Ny);

        % examples
        obj.setCameraROI('2560 x 2160');
        obj.setCameraROI(2560,2160);


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.setCameraROI(size)``  sets the dimensions of the active area of the camera sensor according to the *character* array ``size``, in the form ``size='2560 x 2160'``, ``size='2064 x 2048'``, etc.

    ``obj.setCameraROI(n)``  sets the dimensions of the active area to ``Nx`` columns and ``Ny`` rows.
