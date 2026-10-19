.. dropdown:: **figure** |subTitle| Displays the 4 images of the Jones Matrix coefficients. |/subTitle|

    .. raw:: html
      
        <p class="title">Syntax</p>

    .. code-block:: matlab

        obj.figure()
        hfig = obj.figure();
        hfig = obj.figure(Name, Value);

        % examples
        hfig = obj.figure();
        hfig = obj.figure("func", abs);
        hfig = obj.figure("func", angle);
        hfig = obj.figure("clim", {[0.8 1.02],[0 0.05],[0 0.05],[0.8 1.02]});

    .. raw:: html
      
        <p class="title">Description</p>

    ``obj.figure()`` displays the 4 images of the modulus of the Jones Matrix coefficients, as below.

    .. figure:: /images/JonesMatrixDisplay.png
        :width: 400
        :align: center

    |hr|

    ``obj.figure("func", val)`` where ``val`` should correspond to a predefined matlab function, to be applied to all the displayed image. Indeed, the images are complex and can't be displayed. The default value is ``val = abs``, to display the modulus of the coefficients, but other functions can be used, for instance ``angle``.

    ``obj.figure("clim", cellArray)`` where ``cellArray`` should be a 4-cell array, each containing 2-double vectors defining the clim of each axis (the range of values in the color scales).

        
    If the |ImageJonesMatrix| object ``J`` is an array, then one can switch from one image to another by pressing the left and right arrow keys of the keyboard.