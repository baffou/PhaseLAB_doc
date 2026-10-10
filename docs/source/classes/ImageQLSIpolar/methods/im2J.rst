.. dropdown:: **im2J** |subTitle| Converts a 2-vector of ImagePolar objects into a Jones Matrix object. |/subTitle|

    .. raw:: html
    
        <p class="title">Syntax</p>

    .. code-block:: matlab

        J = obj.im2J()
        JList = objList.im2J()

        % examples
        pIm = [pImL, pImR]; % mix of LCP and RCP illuminations
        J = pIm.im2J();



    .. raw:: html
      
        <p class="title">Description</p>

    ``J = obj.im2J()`` involves a ``(:,2)`` vector of ImagePolar objects, the first column supposed to be associated to a left-handed circularly polarized (LCP) illumination, and the second to a right-handed circularly polarized (RCP) illumination. The method returns the computed Jones Matrix, as a |ImageJonesMatrix| object. ``obj`` can be a list of ``N`` 2-objects, that is a ``(N,2)`` object, and ``J`` a list of ``N`` |ImageJonesMatrix| objects.

    
    |hr|
    