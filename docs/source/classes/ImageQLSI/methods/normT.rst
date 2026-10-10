.. dropdown:: **normT** |subTitle| Applies a correction factor to the T image. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        obj.normT()
        obj.normT(Name, Value)
        objList.normT(___)
        obj2 = obj.normT(___);
        [obj2, params] = obj.normT(___);

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.normT()`` applies a multiplication factor to the ``T`` image. It is usedful when for some reason, the intensity of the light source varied since the reference acquisition. This multiplication factor is computed as the inverse of an average value computed on the selected area.

    |hr|

    Object *vectors* can also be used with this method. The transformation applies then to all the objects of the vector, with the same reference area and same options.

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
            
            obj.normT(___,'Center','Manual','Size',300)
  

    - :matlab:`'Center'`

        With :matlab:`normT(___,'Center','Manual')`, the user has to first click on the center of the reference area. If the argument is set to :matlab:`'Auto'`, then this step is skipped, and the center is automatically set to the center of the image. Also, the user can indicate the coordinates of the center using :matlab:`normT(___,'Center',[x_c, y_c])`.

    - :matlab:`'Size'`

        With :matlab:`normT(___,'Size','Manual')`, once the center is defined (either manually or automatically), the user has to click on the figure to define the shape of the area, around the center point. The user can also indicate the dimensions of the reference area using :matlab:`normT(___,'Size',Npx)` for a square area, or  :matlab:`normT(___,'Size',[Nx, Ny])` for a rectangular area.

    - :matlab:`'twoPoints'`

        Instead of using the :matlab:`'Center'` and :matlab:`'Size'` keywords, one can also click on two opposite corners of the reference area, using :matlab:`normT(___,'twoPoints',true)`.

    - :matlab:`'params'`

        One can also direclty write the coordinates of the area, using :matlab:`normT(___,'params', [x1, x2, y1, y2])`. In this case, no figure opens.

    - :matlab:`'method'`

        Once the area is defined, there are different ways to extract the value on this area. The ``method`` option tells how to proceed. :matlab:`'method = mean'` simply computes the average value over the selected area. :matlab:`'method = median'` computes the median value. :matlab:`'method = boundaryMedian'` compute the median over the values at the edges of the area.  :matlab:`'method = histrogramMode'` compute the value that corresponds to the maximum of the histogram over the selected area.


    Here is an example of a code that manually ajusts the offset of a first object, and applies automatically the same adjustment to a second object:

    .. code-block:: matlab

        [IMc(1) params] = IM(1).normT('Center', 'Manual', 'Size', 'Manual');
        IMc(2) = IM(2).normT('params', params);
    
    Note that this code is equivalent to:

    .. code-block:: matlab

        IMc = IM.normT('Center', 'Manual', 'Size', 'Manual');




