.. dropdown:: **ImageEM** |subTitle| Turns an ImageQLSI object into an ImageEM object. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        obj2 = obj.ImageEM(IMref)
        obj2 = obj.ImageEM(______, Name, Value)

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.ImageEM(IMref)`` uses an **ImageEM** object (``obj``) defining a complex light wave, along with another **ImageEM** object (``IMref``) defining the incident complex light wave, to compute an ImageQLSI, experiment-like, image. By default, this process does not create new variables that may take much space in the RAM. It mainly does :matlab:`obj2.IM = IM`.


    .. raw:: html
      
        <p class="title">Name-value arguments</p>
  

    - :matlab:`'pointingToIM'`

        This boolean value is bu default true. It says that the object is incorporated in the the output ImageEM object to save memory. If we rather choose to make a stand-alone ImageEM object, this value should be set to false:

    .. code-block:: matlab

        IMem = IM.ImageEM("pointingToIM", false);
