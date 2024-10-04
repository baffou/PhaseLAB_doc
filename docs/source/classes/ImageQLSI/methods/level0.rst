.. dropdown:: **level0** |subTitle| Offset the OPD image to adjust the background value to zero. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>

    .. code-block:: matlab

        obj.level0()
        obj.level0(Name, Value)
        objList.level0(___)
        obj2 = obj.level0(___);
        [obj2, params] = obj.level0(___);

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.level0()`` adjusts the offset of the image. More precisely. This method asks for an area on the image, the average value of which should be zero. The method applies an offset to the whole image to satifies this condition. Many options can be specified to tell how this area is selected. See below.

    |hr|

    Object *vectors* can also be used with this method. The transformation applies then to all the objects of the vector, with the same reference area.

    |hr|

    If an output is used, ``obj2``, then the object is not modified, but duplicated.

    |hr|

    If a second output is specified, then the area parameters are returned as a 4-vector ``params = [x1, x2, y1, y2]``;
    

    .. raw:: html
      
        <p class="title">Name-value arguments</p>
  
    .. note::
    
        Specify optional pairs of arguments as ``Name1 = Value1, ..., NameN = ValueN``, where ``Name`` is the argument name and ``Value`` is the corresponding value. Name-value arguments must appear after other arguments, but the order of the pairs does not matter.

        Example:

        .. code-block:: matlab
            
            obj.level0(___,'Center','Manual','Size',300)
  

    - :matlab:`'Center'`

        With :matlab:`level0(___,'Center','Manual')`, the user has to first click on the center of the reference area. If the argument is set to :matlab:`'Auto'`, then this step is skipped, and the center is automatically set to the center of the image. Also, the user can indicate the coordinates of the center using :matlab:`level0(___,'Center',[x_c, y_c])`.

    - :matlab:`'Size'`

        With :matlab:`level0(___,'Size','Manual')`, once the center is defined (either manually or automatically), the user has to click on the figure to define the shape of the area, around the center point. The user can also indicate the dimensions of the reference area using :matlab:`level0(___,'Size',Npx)` for a square area, or  :matlab:`level0(___,'Size',[Nx, Ny])` for a rectangular area.

    - :matlab:`'twoPoints'`

        Instead of using the :matlab:`'Center'` and :matlab:`'Size'` keywords, one can also click on two opposite corners of the reference area, using :matlab:`level0(___,'twoPoints',true)`.

    - :matlab:`'params'`

        One can also direclty write the coordinates of the area, using :matlab:`level0(___,'params', [x1, x2, y1, y2])`. In this case, no figure opens.

    Here is an example of a code that manually ajusts the offset of a first object, and applies automatically the same adjustment to a second object:

    .. code-block:: matlab

        [IMc(1) params] = IM(1).level0('Center', 'Manual', 'Size', 'Manual');
        IMc(2) = IM(2).level0('params', params);
    
    Note that this code is equivalent to:

    .. code-block:: matlab

        IMc = IM.level0('Center', 'Manual', 'Size', 'Manual');




