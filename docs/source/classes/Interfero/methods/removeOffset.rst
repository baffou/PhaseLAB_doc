.. dropdown:: removeOffset |subTitle| Substract an number, or an image to the interferogram image. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        obj.removeOffset()
        obj.removeOffset(val)
        obj2 = obj.removeOffset(___);


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.removeOffset()`` removes from ``Itf``, by default, the value of the pixel of weakest intensity in the ``Itf`` image.

    |hr|

    ``obj.removeOffset(val)`` remove ``val``, which can be a number, or a matrix of the same size as ``Itf``.
    
    |hr|

    If an output argument ``obj2`` is specified, ``obj`` is not modified, but duplicated.
    
    .. note::

        If it exists, it also removes the offset of the Reference image.

    .. warning::

        Make sure you don't use this method twice. It is recommended to rather measure a dark image, and subtract it to the interferogram images using the option :matlab:`'DarkImage' = Itf_dark` in the :ref:`QLSIprocess <The_QLSIprocess_method>` method.


