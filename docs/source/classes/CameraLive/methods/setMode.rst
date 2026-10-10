
.. dropdown:: **setMode** |subTitle| Sets the acquisition mode. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototypes
        obj.setMode(cycleMode, triggerMode)

        % examples
        obj.setMode('Fixed', 'External')
        obj.setMode('Continuous', 'Internal')


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.setMode(cycleMode, triggerMode)``  sets the cycle mode and the trigger mode of the camera. The possible values of ``cycleMode`` are ``'Fixed'``, ``'Continuous'``, and ``'Burst'``. The possible values of Trigger are ``'Internal'``, ``'External'``, ``'Software'``.

