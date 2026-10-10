.. dropdown:: **setThetaShift** |subTitle| Shifts the origin of the polarization ellipse angle. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        objList.setThetaShift(val)

        % examples
        objList.setThetaShift(pi/2) % Set (y) axis to be the origin of the polar ellipse angle



    .. raw:: html
      
        <p class="title">Description</p>

    ``objList.setThetaShift(val)`` subtracts ``val`` to the returned polarization ellipse angle property ``thetaEllipse``. The common use is to set ``val = pi/2`` so that the angle is defined compared with the vertical :math:`(y)` axis.

    
    |hr|
    