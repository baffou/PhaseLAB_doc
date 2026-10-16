.. dropdown:: **im2T** |subTitle| Converts a 2-vector of ImageQLSIpolar objects into complex eigen-transmittance images. |/subTitle|

    .. raw:: html
    
        <p class="title">Syntax</p>

    .. code-block:: matlab

        T = obj.im2T()
        Tlist = objList.im2T()

        % examples
        pIm = [pImL, pImR]; % mix of LCP and RCP illuminations
        T = pIm.im2T();

    .. raw:: html
      
        <p class="title">Description</p>

    ``T = obj.im2T()`` involves a ``(:,2)`` vector of ImageQLSIpolar objects ``obj``, the first column supposed to be associated to a left-handed circularly polarized (LCP) illumination, and the second to a right-handed circularly polarized (RCP) illumination. The method returns an |ImageTransmittance| object ``T``.

    
    |hr|
    