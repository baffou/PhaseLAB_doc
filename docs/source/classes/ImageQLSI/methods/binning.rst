.. dropdown:: **binning** |subTitle| Performs 2x2 or 3x3 or 4x4 pixel binning of the images of the ImageQLSI object. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        obj.binning()
        obj.binning(n)
        obj2 = obj.binning(___);


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj`` can be a vector of *ImageQLSI* objects. In that case, the treatment will be performed on all the objects of the list.

    ``obj.binning()`` performs, by default, a 3x3 binning of the images of ``obj``.

    |hr|

    ``obj.binning(n)`` performs, :math:`n\times n` binning of the images of ``obj``. Only works with ``n = 2``, ``n = 3``, or ``n = 4``.
    
    |hr|

    If an output argument is specified, ``obj`` is not modified, but duplicated.
    




