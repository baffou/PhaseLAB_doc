.. dropdown:: **propagation** |subTitle| Performs a numerical propagation of the field over a specified distance, as a means to perform numerical refocusing. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    

    .. code-block:: matlab

        obj.propagation(z)
        obj.propagation(____, Name, Value)
        obj2 = obj.propagation(____, Name, Value)


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.propagation(z)`` propagates the E field at the object plane over a distance ``z``. The resulting field corresponds to the image refocused by a distance ``z``. 

    |hr|

    .. raw:: html
      
        <p class="title">Name-value arguments</p>
  
    .. note::
    
        Specify optional pairs of arguments as ``Name1 = Value1, ..., NameN = ValueN``, where ``Name`` is the argument name and ``Value`` is the corresponding value. Name-value arguments must appear after other arguments, but the order of the pairs does not matter.

        Example:

        .. code-block:: matlab
            
            obj.propagation(1e-6, "n", 1.33)
  

    - :matlab:`'n'`

        Specifies the refractive index in which the field propagates. If not specified, the medium defined in the **Illumination** object used to compute the images is used.

    - :matlab:`'dx'` and :matlab:`'dy'`

        ``dx`` and ``dy`` laterally translate the propagated optical field in \(x\) and \(y\), by a possibly non-integer number of pixels. For instance

    .. code-block:: matlab

        IM.propagate('dx', 2.3e-6, 'dy', -3.1e-6);


