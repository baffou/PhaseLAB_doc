.. dropdown:: **cancelGradients** |subTitle| Delete the DWx and DWy properties, to save RAM |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        obj.cancelGradients()

    .. raw:: html
      
        <p class="title">Description</p>

    When computing the ``OPD`` and ``T`` images using the ``QLSIprocess`` method of the |Interfero| class, using the option :matlab:`"saveGradient" = true`, the two wavefront gradient images are stored in the properties ``DWx `` and ``DWy``. The method ``cancelGradients`` deletes the content of these properties. The aim can be to save computer RAM.

