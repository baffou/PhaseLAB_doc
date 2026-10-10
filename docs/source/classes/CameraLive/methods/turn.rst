
.. dropdown:: **turn** |subTitle| turns on or off the camera on the Matlab side. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>
    
    .. code-block:: matlab

        % prototypes
        obj.turn(state);

        % examples
        obj.turn('on');
        obj.turn('off');


    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.turn(state)`` . With ``state = 'on'``, it does all the necessary steps to prepare the camera, in particular, it creates the camera handle variable, initializes the library, turns off sensor cooling (in the case of an sC8 camera). With ``state = 'off'``, it closes everything and releases memory.

