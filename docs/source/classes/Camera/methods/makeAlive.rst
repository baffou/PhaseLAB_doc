
.. dropdown:: **makeAlive** |subTitle| Upgrade the Camera with a set of new properties and methods so that it can be operated in LIVE mode. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototypes
        obj.makeAlive();

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.makeAlive()``  turns the **Camera** object into a **CameraLive** object (daughter class) that contains additional properties and methods to operate the camera in live mode, such as ``obj.expTime``,  ``obj.turn('on')``` , ``obj.startAcqusition()``, etc. See the |CameraLive| class. This class in used in the LIVE app.














