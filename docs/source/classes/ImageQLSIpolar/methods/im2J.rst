.. dropdown:: **im2J** |subTitle| Converts a 2-vector of ImageQLSIpolar objects into a Jones Matrix object. |/subTitle|

    .. raw:: html
    
        <p class="title">Syntax</p>

    .. code-block:: matlab

        J = obj.im2J();
        J = im2J(objL, objR);

        % examples
        pIm = [pImL, pImR]; % mix of LCP and RCP illuminations
        J = pIm.im2J();
        J = im2J(pImL, pImR);



    .. raw:: html
      
        <p class="title">Description</p>

    ``J = obj.im2J()`` involves a ``(:,2)`` vector of **ImageQLSIpolar** objects. The first column should be associated to a :abbr:`LCP (left-handed circular polarization)` illumination, and the second to a :abbr:`RCP (right-handed circular polarization)` illumination. The method returns the computed Jones Matrix, as a |ImageJonesMatrix| object. ``obj`` can be a list of ``N`` 2-objects, that is a ``(N,2)`` object, and ``J`` a list of ``N`` |ImageJonesMatrix| objects. The method can also be used with two inputs, the :abbr:`LCP (left-handed circular polarization)` and :abbr:`LCP (left-handed circular polarization)` **ImageQLSIpolar** objects.
    
    |hr|
    