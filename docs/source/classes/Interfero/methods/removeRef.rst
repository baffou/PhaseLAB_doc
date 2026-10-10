.. dropdown:: removeRef |subTitle| Delete the ``Ref`` property from the object. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        obj.removeRef()
        obj2 = obj.removeRef()


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.removeRef()`` removes the ``Ref`` property from the object, originally assigned using the ``Reference()`` method.

    |hr|

    If an output argument ``obj2`` is specified, ``obj`` is not modified, but duplicated.

