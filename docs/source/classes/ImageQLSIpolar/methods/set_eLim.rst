.. dropdown:: **set_eLim** |subTitle| Sets the limit ellipticity value, used for image display. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        objList.set_eLim(val)

        % examples
        objList.set_eLim(0.8)



    .. raw:: html
      
        <p class="title">Description</p>

    ``objList.set_eLim(val)`` assigns ``val`` to the object property ``eLim``. This property is used when the ellipticity image needs to be exported, or displayed using the ``figure`` method and the associated GUI. The value range from 0 to 1.

    
    |hr|
    