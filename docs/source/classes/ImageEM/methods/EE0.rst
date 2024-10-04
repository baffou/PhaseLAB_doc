.. dropdown:: **EE0** |subTitle| Return the value of the incident field at the center of the field of view. |/subTitle|

    .. raw:: html
      
        <p class="title">Synthax</p>
    
    .. code-block:: matlab

        val = obj.EE0()

    .. raw:: html
      
        <p class="title">Description</p>

    This method returns the value of the incident field, at the center of the field of view, at the sample plane (not at the image plane), at :math:`z=0`. If ``obj`` is already an incident field, it simply returns its value at the center of the field of view.

