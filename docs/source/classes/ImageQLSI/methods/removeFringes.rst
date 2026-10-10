.. dropdown:: **removeFringes** |subTitle| Removes unwanted fringes on the OPD image. |/subTitle|


    .. raw:: html
      
        <p class="title">Syntax</p>
    

    .. code-block:: matlab

        obj.removeFringes(Name, Value)
        objList.removeFringes(Name, Value)
        obj2 = obj.removeFringes(Name, Value)
        [obj2, mask] = obj.removeFringes(Name, Value)

    .. raw:: html
      
        <p class="title">Description</p>

    In some cases, artefactual fringes can appear on a reconstructed OPD image. It happens typically when the QLSI grating has moved after taking the reference. ``obj.removeFringes()`` can remove these fringes by suppressing spots in the Fourier transform of the image. The method opens up a window of the Fourier transform of the OPD image. The user has to click twice per spot: a first time to define the center of the spot and and a second time to define its radius. This operation can be repeated several times. Once over, press enter to exit the procedure and apply the changes.

    |hr|

    ``obj.removeFringes()`` applies a high-pass filter on the spatial frequencies of the image.
    
    |hr|

    ``objList.removeFringes()``: if an array of objects is used, then the same modification applies to all the objects.

    |hr|

    ``obj2 = obj.removeFringes()``: if an output is specified, the object is not modified but duplicated.
    
    |hr|

    ``[obj2, mask] = obj.removeFringes()``: the second output returns the mask that the use has generated.
    
    |hr|

    ``obj.removeFringes("mask", mask)``: This mask can be applied again to other object using the option ``mask``.
    
     |hr|

    ``obj.removeFringes("props", 'T')``: specify whether the mask applies to the OPD image (``"props", 'W'``) or the T image (``"props", 'T'``).
    
   

