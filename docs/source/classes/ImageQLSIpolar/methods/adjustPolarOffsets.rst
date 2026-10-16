.. dropdown:: **adjustPolarOffsets** |subTitle| Automatically adjusts the relative wavefront offsets between the 4 wavefront images. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        objList.adjustPolarOffsets(Name, Value)

        % examples
        objList.adjustPolarOffsets()
        objList.adjustPolarOffsets("method", 'manual')
        objList.adjustPolarOffsets("display", true)

    .. raw:: html
      
        <p class="title">Description</p>

    ``objList.adjustPolarOffsets()`` automatically sets the wavefront relative offset of the 4 polar images. :matlab:`objList.adjustPolarOffsets("method", 'manual')` enables the user to use the image area that is supposed to correspond to zero phase value (usually the area outside of the image object). :matlab:`objList.adjustPolarOffsets("display", true)` automatically sets the wavefront relative offset of the 4 polar images, but displays in the meantime the C images to check if the algorithm does a good job. See Ref. \ [#ACSNanoaccepted]_ for more details.


    .. [#ACSNanoaccepted] *Single-shot polarization imaging of vectorial metasurfaces using cross-grating wavefront microscopy*, J. Flamant, B. Marthy, K. Zangeneh Kamali, N. Ullberg, G. Demesy, P. Ferrand, M. Käll, G. Baffou, **ACS Nano**, accepted (2026)
    
    
    
    |hr|
    